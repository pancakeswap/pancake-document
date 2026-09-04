---
description: '2026-09-04'
---

# RWA Capital Inefficiency — and How Shared Inventory Solves for it

A PancakeSwap case study experiment (Part 1: The Setup)

<figure><img src="../../../../.gitbook/assets/image (217).png" alt=""><figcaption></figcaption></figure>

This is the first part in a two-part case study. In this part, we lay out the real capital efficiency problem RWA asset issuers face, introduce how the Shared Inventory Hook (SIH) by PancakeSwap is meant to solve it, and introduce a live case study experiment to test it with onchain data.

Over the next few weeks, we publish Part 2: The Results.

***

### 🧩 What is the Capital Efficiency Problem?

The RWA industry loves one number: **how much has been tokenized.** It's the headline on almost every report - a new asset class arriving, billions issued, 100s of percentage growth.

There's a second number that gets buried though, which might be a more prominent signal: **how much of it can actually be traded?**

The gap between those two is where it’s at. On the canonical tracker, [rwa.xyz](http://rwa.xyz), the amount of value _represented_ onchain dwarfs the amount that can be _transacted_ against at any given moment — the data shows locked, reference, and distributed value running **more than an order of magnitude larger than what sits in tradable books.**

<figure><img src="../../../../.gitbook/assets/image (380).png" alt=""><figcaption></figcaption></figure>

_Source: app.rwa.xyz/stocks_

For an RWA issuer, this is the trap. Tokenizing a stock, an ETF, or a treasury is the easy part - getting it to trade tightly and reliably is the challenge, and it's where capital efficiency lives or dies. The ultimate goal is to let traders _actually tra&#x64;_&#x65; the tokenized asset easy and cheap - that’s ultimately where the volume and fees come from.

And here's why it's specifically a _capital-efficiency_ problem, not just a liquidity one.

#### Every pool quoted demands its own exclusive USDT stack

To make one RWA pair tradable in a traditional concentrated liquidity (CLAMM) pool, issuers need dedicated quote-asset — USDT — sitting there for buyers to sell into. List ten pairs, and the CLAMM model requires funding of **ten separate USDT stacks**, one stack per pair, none of them able to help each other. So quote capital gets shredded into exclusive silos.

We measured it on our own book. We took **7 tokenized-equity pools live on PancakeSwap** (each running a traditional V3 CLAMM pool) and pulled the exclusive USDT.

Snapshot: **2 September 2026.**

<table data-search="false"><thead><tr><th>Pair</th><th>Exclusive USDT in pool</th><th>Pool TVL</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Total</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

That's **\~$745k of USDT exclusively allocated.**

And this is only the names that have a book.

SNXXB, KORUB, SOXSB, and DJTB have no CLAMM USDT book at all — tokenized, but hard to trade.

***

### 🎯 What should an Issuer be Optimizing for?

Strip away the mechanics and an RWA issuer must solve for three things at the core:

1. **Their asset to be truly and efficiently tradable** — tight quotes on every asset, not just flagship tokens.
2. **The least capital possible** tied up doing it — Quote-asset is expensive; funding ten stacks of USDT exclusively is not very efficient.
3. **Not to run a trading desk —** To issue assets without needing to operate liquidity infrastructure every day.

So the question is whether liquidity can be structured differently — and that's what the Shared Inventory Hook by PancakeSwap is designed to solve.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH is a PancakeSwap Infinity hook that lets an RWA issuer back many pairs from one shared USDT pot instead of one exclusive stack per pair.**

SIH does this by providing liquidity just-in-time, enabling:

* Deeper quotes on pairs
* Lower price impact, especially on large ticket trades
* Freed up capital for RWA issuers since less capital deployed quotes more pairs

Let’s look at these claims in practice.

As of the same **2 September 2026** snapshot, SIH holds **$635,028** of inventory in a single hook, quoting **11 pairs** from **$180,467** of shared USDT, running at **87.7%** utilization. With this, SIH has processed **$3.56M across 17,299 transactions.**

So that is **one shared USDT balance of \~$700k quoting across \~11 pairs versus \~$745k quoting only 7 pairs**.

Same job, only designed to stop duplicating capital.

<figure><img src="../../../../.gitbook/assets/image (381).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (395).png" alt=""><figcaption></figcaption></figure>

Mapped back to what issuers care about:

* N exclusive USDT balances traditionally → ✅ one shared pot with SIH
* Issued but not tradable → ✅ tradable\
  Shared inventory injecting just-in-time around the live price means tokens that have no V3 USDT book can still be quoted, not just minted.
* Operating a desk → ✅ a permissioned operator\
  The issuer supplies inventory; the hook and its operator handle the quoting.

***

### 🔬 Try the Shared Inventory Simulator

Build intuition for how SIH behaves with our interactive comparison tool **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="../../../../.gitbook/assets/image (406).png" alt=""><figcaption></figcaption></figure>

This is a **high-level, normalised comparison** of SIH against a traditional CLAMM book — a number of real-world factors are held constant on both sides so the capital-efficiency mechanic can be isolated cleanly. It's a model for understanding, not a P\&L.

Three tabs:

* **Simulator tab** - play with inventory, band width, and flow to see how SIH _would_ perform against a comparable CLAMM pool under different conditions.
* **Comparison tab** - SIH set directly against a **PancakeSwap V3 CLAMM** book on the same pools, so you can see the shared USDT pot-vs-exclusive USDT difference in capital committed and coverage side by side.
* **Live data tab** — measure how SIH is _actually_ performing right now, pulled from the onchain queries powering this study.

The simulator is aimed to help demonstrate how the Shared Inventory Hook operates. Try it, then measure it against the real results we publish in the next couple of weeks.

***

### 🧪 The Experiment

Over the **next few weeks** we run SIH live and measure it against the capital-efficiency claims above, using onchain sources. Every week we will drop new info-bites on SIH performance and its architecture.

**Live RWA pairs in the study:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Note: SNXXB, KORUB, SOXSB, and DJTB have no traditional CLAMM book at all._

**We will publish the results over the next few weeks on PancakeSwap’s** [**Twitter.**](https://x.com/PancakeSwap)

The results published will cover:

* **The full performance dataset -** All SIH data over next few weeks, combined into one picture.
* **The capital allocation question -** How much capital SIH actually saved an RWA issuer.
* **Beat / miss -** Where SIH outperformed expectations, and where it needs work.
* **The verdict -** A grounded conclusion on how effective SIH really is for RWA capital efficiency.

_A note on data: Figures here are drawn from live onchain queries and public pair data, cited inline. Some comparisons use different windows and we've flagged those — the study is designed to measure like-for-like where this intro could only frame the question._

***

### Want to enable SIH on your assets?

If you’re a RWA issuer and you're tired of funding a separate USDT stack for every pool you quote, this is for you.

We're onboarding RWA issuers now. Fill out this google form and we'll walk you through getting your asset quoted on SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Thanks for reading! Follow us on [X](https://x.com/PancakeSwap) for the latest updates, and join the conversation on [Telegram](https://t.me/PancakeSwap) and [Discord](https://discord.gg/pancakeswap).

Let’s build,\
The Chefs 🥞

***

_Disclaimer: This content is for general information and educational purposes only. It should not be construed as financial, legal, or other professional advice. Digital asset prices can be volatile. The value of your investment may go down or up._
