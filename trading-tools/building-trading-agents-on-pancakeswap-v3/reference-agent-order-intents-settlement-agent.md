# Reference Agent — Order/Intents Settlement Agent

> एक ERC-8183 Provider agent जो PancakeSwap aggregation के माध्यम से एक समय में एक swap-intent Job को fulfill करता है और target token को सीधे Client को deliver करता है।

### 0. यह ERC-8183 पर कैसे map होता है

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) तीन roles और states Open → Funded → Submitted → Terminal के साथ एक **Job** define करता है। BNB का **BNBAgent SDK** live implementation है।

| Role                                               | इस agent में                                                                                                                     |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Client** (Agent-A)                               | एक swap intent post करता है: "X of token A → token B swap करें, मुझे ≥ `minOut` deliver करें", input + tip escrow करता है      |
| **Provider** (Agent-B) — **यह हमारा reference agent है** | **PancakeSwap aggregation** के माध्यम से quote करता है, और यदि `minOut` meet/beat कर सकता है, तो swap execute करता है और Client को token B deliver करता है |
| **Evaluator**                                      | verify करता है कि Client को token-B amount ≥ `minOut` मिला; tip release करता है (या Client को refund करता है)                    |

Deliverable objective है ("क्या Client को ≥ `minOut` मिला?"), जो यही कारण है कि यह ERC-8183 में fit होता है।

***

### 1. Purpose और one-line scope

> एक **Provider** agent जो PancakeSwap aggregation के माध्यम से एक समय में एक swap-intent Job को fulfill करता है और target token को सीधे Client को deliver करता है — और कुछ नहीं।

***

### 2. Agent को क्या करने की ALLOWED है (capability allowlist)

| # | Capability           | Surface                                                    | Notes                                                                      |
| - | -------------------- | ---------------------------------------------------------- | -------------------------------------------------------------------------- |
| A | Open Jobs discover करना | BNBAgent SDK (ERC-8183 registry)                           | Read-only; swap-intent Jobs filter करें जो serve कर सके                    |
| B | Route quote करना     | **PancakeSwap aggregation** (Aggregator API / Smart Router) | Read-only; V3 में best price                                               |
| C | Job accept करना      | BNBAgent SDK (Funded → committed)                          | केवल यदि fresh quote ≥ `minOut` और tip ≥ floor हो                          |
| D | Swap execute करना    | PancakeSwap router                                         | Job escrow से input pull; **output recipient = Client**, एक tx में          |
| E | Deliverable submit करना | BNBAgent SDK (→ Submitted)                                | proof के रूप में settlement tx hash                                         |
| F | Tip claim करना       | ERC-8183 escrow / x402                                     | केवल Evaluator द्वारा Job Terminal mark करने के बाद                         |

**हर settlement का output सीधे Client को जाता है। Agent की एकमात्र कमाई Job का tip है।**

***

### 3. Hard guardrails (featuring का gate)

| Guardrail                           | Rule                                                                                                                                                           |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **जो fulfill नहीं कर सकते उसे accept न करें** | Job तभी accept करें जब _fresh_ quote `minOut` clear करे। यदि नहीं कर सकता, Job को Funded दूसरे Provider के लिए छोड़ें।                                         |
| **Execution पर Requote करें**       | Settle करने से तुरंत पहले re-quote करें; abort करें यदि route अब `minOut` clear नहीं करता (stale quotes नहीं)।                                                 |
| **Atomic settlement**               | Pull-from-escrow → swap → Client को deliver **एक transaction** में, output recipient = Client। Agent को Client के funds को किसी failed step में कभी hold नहीं करना चाहिए। |
| **Slippage**                        | Execution slippage bounded; delivered amount slippage के बाद भी ≥ `minOut` होनी चाहिए, या tx revert होगी। कभी `amountOutMin = 0` नहीं।                         |
| **Deadline**                        | Settlement tx पर short deadline (≤ 5 min); Job की अपनी deadline का सम्मान करें।                                                                               |
| **Min tip / max value**             | Tip floor से नीचे या per-Job value cap से ऊपर Jobs accept न करें।                                                                                              |
| **Token safelist**                  | केवल उन Jobs को serve करें जिनके tokens PancakeSwap token list पर हैं (anti-honeypot / fake-token)।                                                             |
| **Single-Job concurrency (v1)**     | एक समय में एक Job fulfill करें; over-commitment नहीं।                                                                                                          |
| **Gas precondition**                | Accept करने से पहले full settlement के लिए पर्याप्त BNB confirm करें।                                                                                           |
| **Idempotent**                      | किसी Job को जो already Submitted/Terminal है उसे double-submit या re-fulfill न करें।                                                                             |

यदि कोई rule meet नहीं हो सकती, **Job skip करें** — settlement कभी force न करें।

***

### 4. Out of scope — agent को क्या नहीं करना चाहिए

1. **Client funds को specified swap के अलावा किसी चीज के लिए उपयोग करें।** Output recipient हमेशा Client है।
2. **अपनी inventory front करें / principal risk लें।** v1 **escrow-pull only** है — यह Client के escrowed input को route करता है; अपनी balance से fill नहीं करता।
3. **Non-PancakeSwap या unverified contracts के माध्यम से route करें**, या PancakeSwap aggregation के बाहर settle करें।
4. **Non-safelisted tokens वाली Jobs serve करें**, या (v1) कोई scaled-UI / RWA token (§5)।
5. **Leverage, perps, margin, या lending उपयोग करें।**
6. **एक deliverable submit करें जो वास्तव में fulfill नहीं किया** (false attestation नहीं) या **अपनी Jobs evaluate करें** (conflict of interest)।
7. PancakeSwap या ERC-8183 contracts पर कोई **owner/admin function call करें**।
8. **Single settlement से परे standing token approvals रखें**; approvals को Job amount तक scope करें।

***

### 5. PancakeSwap-specific logic (application correctness)

* **PancakeSwap aggregation के माध्यम से Route करें**, single pool से नहीं — V2 / V3 / Stable में best execution ही पूरा value proposition है ("best price tip जीतता है")।
* Router के `recipient` को Client address सेट करके **atomically Client को deliver करें**; कभी two-step "swap to self, then transfer" नहीं।
* **Quote freshness** — discovery और settlement के बीच on-chain price move होती है; execution पर requote करें (guardrail §3)।
* **`minOut` raw units में है।** **Scaled-UI / ERC-8056 tokens** (Binance Stock Tokens / RWA equities) के लिए raw ≠ displayed; गलत handling silently mis-deliver करती है। **Scaled-UI tokens को v1 से exclude करें** जब तक engineering raw-unit handling end-to-end confirm न करे।
* Settlement swap पर **Slippage minimum** इस तरह derived होनी चाहिए कि _delivered_ amount, tip/fee split को accounting करने के बाद ≥ `minOut` हो।

***

### 6. Failure और recovery behavior

* **Execution पर Quote `minOut` fail करता है** → escrow pull के पहले/atomically abort करें; Job अन्य Provider के लिए Funded रहती है। कोई partial state नहीं।
* **Already Submitted/Terminal** → skip करें (idempotent)।
* **Settlement tx revert होती है** → Job दूसरों के लिए claimable रहती है; agent failure record करता है और आगे बढ़ता है।
* **किसी Job पर बार-बार failures** → उस Job को locally blacklist करें और alert करें, retry-looping के बजाय।

***

### 7. Integration points (BNB / ERC-8183 का हिस्सा)

ये BNB Agent Studio / BNBAgent SDK द्वारा provide किए जाते हैं, PancakeSwap द्वारा नहीं build किए — लेकिन spec इन पर निर्भर है:

* **Job lifecycle** (Open discover → Funded accept → Submitted → claim) BNBAgent SDK के माध्यम से।
* **Provider identity** ERC-8004 के माध्यम से।
* **Escrow + payout** ERC-8183 escrow / x402 के माध्यम से।
* **Evaluator** — predicate यह होनी चाहिए "Client का token-B balance ≥ `minOut` बढ़ा।" BNB के साथ confirm करें **कि Evaluator कौन run करता है** (neutral/protocol vs. Client) और कि predicate on-chain enforceable है।

***

### 8. Recommended v1 posture और open decisions

1. **Escrow-pull only, single Job at a time, token-safelist only, no scaled-UI tokens।** Launch पर feature करने के लिए सबसे छोटी safe surface।
2. **PancakeSwap swap interface confirm करें** — **Aggregator (`aggr`) HTTP API** vs **Smart Router SDK**। Jerry के note में कहा है "use pcs aggr api"; confirm करने की जरूरत है कि agent किसे call करता है, क्योंकि यह integration बदलता है (और क्या guide को aggregation section की जरूरत है)।
3. **Escrow mechanic BNB के साथ confirm करें** — क्या Provider Client के escrowed input को swap route करने के लिए pull कर सकता है, और क्या delivery-to-Client deliverable के रूप में enforceable है?
4. **Evaluator owner और predicate confirm करें** (§7)।

> Featuring से पहले Eng sign-off: atomic escrow-pull → swap → deliver-to-Client routing; requote-at-execution; `minOut`-after-slippage math; safelist enforcement; idempotent Job handling।
