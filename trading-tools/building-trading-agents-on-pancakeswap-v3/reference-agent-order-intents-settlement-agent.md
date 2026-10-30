# Reference Agent — Order/Intents Settlement Agent

> Một agent Provider theo ERC-8183 thực hiện từng Job swap-intent một, bằng cách định tuyến qua PancakeSwap aggregation và giao token đích trực tiếp cho Client.

### 0. Cách ánh xạ sang ERC-8183

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) định nghĩa một **Job** với ba vai trò và các trạng thái Open → Funded → Submitted → Terminal. **BNBAgent SDK** của BNB là bản triển khai đang hoạt động.

| Vai trò                                                  | Trong agent này                                                                                                                |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Client** (Agent-A)                                     | đăng một swap intent: "hoán đổi X token A → token B, giao cho tôi ≥ `minOut`", ký quỹ khoản đầu vào + một khoản tip           |
| **Provider** (Agent-B) — **đây là reference agent của chúng ta** | báo giá qua **PancakeSwap aggregation**, và nếu có thể đạt/vượt `minOut`, sẽ thực hiện hoán đổi và giao token B cho Client |
| **Evaluator**                                            | xác minh Client đã nhận được lượng token-B ≥ `minOut`; giải phóng tip (hoặc hoàn tiền cho Client)                              |

Sản phẩm giao là khách quan ("Client có nhận được ≥ `minOut` không?"), đó chính là lý do nó phù hợp với ERC-8183 trong khi rebalancer thì không.

***

### 1. Mục đích & phạm vi trong một dòng

> Một agent **Provider** thực hiện từng Job swap-intent một, bằng cách định tuyến qua PancakeSwap aggregation và giao token đích trực tiếp cho Client — và không làm gì khác.

***

### 2. Agent ĐƯỢC PHÉP làm gì (danh sách cho phép năng lực)

| # | Năng lực               | Bề mặt                                                      | Ghi chú                                                                    |
| - | ---------------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------- |
| A | Tìm các Job đang mở    | BNBAgent SDK (ERC-8183 registry)                            | Chỉ đọc; lọc các Job swap-intent mà nó có thể phục vụ                      |
| B | Báo giá một tuyến      | **PancakeSwap aggregation** (Aggregator API / Smart Router) | Chỉ đọc; giá tốt nhất trên V3                                              |
| C | Nhận một Job           | BNBAgent SDK (Funded → committed)                           | Chỉ khi báo giá mới của nó ≥ `minOut` và tip ≥ mức sàn                     |
| D | Thực hiện hoán đổi     | PancakeSwap router                                          | Đầu vào được rút từ escrow của Job; **người nhận đầu ra = Client**, trong một tx |
| E | Nộp sản phẩm giao      | BNBAgent SDK (→ Submitted)                                  | Hash của tx thanh toán làm bằng chứng                                      |
| F | Nhận tip               | ERC-8183 escrow / x402                                      | Chỉ sau khi Evaluator đánh dấu Job là Terminal                             |

**Đầu ra của mọi lần thanh toán đều đi thẳng đến Client. Khoản thu duy nhất của agent là tip của Job.**

***

### 3. Các rào chắn cứng (điều kiện để được giới thiệu)

| Rào chắn                               | Quy tắc                                                                                                                                                           |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Không nhận thứ nó không thể thực hiện** | Chỉ nhận một Job nếu báo giá _mới_ đạt `minOut`. Nếu không, để Job ở trạng thái Funded cho Provider khác.                                                      |
| **Báo giá lại khi thực thi**           | Báo giá lại ngay trước khi thanh toán; hủy nếu tuyến không còn đạt `minOut` (không dùng báo giá cũ).                                                             |
| **Thanh toán nguyên tử**               | Rút từ escrow → hoán đổi → giao cho Client trong **một giao dịch**, người nhận đầu ra = Client. Agent không bao giờ được giữ tiền của Client qua một bước thất bại. |
| **Trượt giá**                          | Trượt giá khi thực thi bị giới hạn; lượng giao vẫn phải ≥ `minOut` sau trượt giá, nếu không tx sẽ revert. Không bao giờ đặt `amountOutMin = 0`.                  |
| **Thời hạn**                           | Deadline ngắn cho tx thanh toán (≤ 5 phút); tuân thủ deadline riêng của Job.                                                                                      |
| **Tip tối thiểu / giá trị tối đa**     | Không nhận các Job có tip dưới mức sàn hoặc giá trị vượt mức trần cho mỗi Job.                                                                                    |
| **Danh sách token an toàn**            | Chỉ phục vụ các Job có token nằm trong danh sách token của PancakeSwap (chống honeypot / token giả).                                                              |
| **Đồng thời một Job (v1)**             | Thực hiện một Job tại một thời điểm; không cam kết quá mức.                                                                                                       |
| **Điều kiện gas**                      | Xác nhận có đủ BNB cho toàn bộ quá trình thanh toán trước khi nhận Job.                                                                                           |
| **Idempotent**                         | Không bao giờ nộp hai lần hoặc thực hiện lại một Job đã ở trạng thái Submitted/Terminal.                                                                          |

Nếu bất kỳ quy tắc nào không thể đáp ứng, **bỏ qua Job** — không bao giờ ép thanh toán.

***

### 4. Ngoài phạm vi — agent KHÔNG ĐƯỢC

1. **Dùng tiền của Client cho bất kỳ việc gì ngoài lần hoán đổi đã chỉ định.** Người nhận đầu ra luôn là Client.
2. **Chạy trước bằng kho của chính nó / chịu rủi ro vốn gốc.** v1 chỉ **rút từ escrow** — nó định tuyến khoản đầu vào đã ký quỹ của Client; không thực hiện từ số dư của chính mình.
3. **Định tuyến qua các hợp đồng không thuộc PancakeSwap hoặc chưa được xác minh**, hoặc thanh toán bên ngoài PancakeSwap aggregation.
4. **Phục vụ các Job có token không nằm trong danh sách an toàn**, hoặc (v1) bất kỳ token scaled-UI / RWA nào (§5).
5. **Dùng đòn bẩy, perps, ký quỹ hoặc cho vay.**
6. **Nộp sản phẩm giao mà nó chưa thực sự hoàn thành** (không xác nhận sai) hoặc **đánh giá Job của chính mình** (xung đột lợi ích).
7. **Gọi bất kỳ hàm owner/admin nào** trên PancakeSwap hoặc các hợp đồng ERC-8183.
8. **Giữ quyền phê duyệt token kéo dài** vượt quá một lần thanh toán; giới hạn phê duyệt trong số lượng của Job.

***

### 5. Logic riêng của PancakeSwap (tính đúng đắn của ứng dụng)

* **Định tuyến qua PancakeSwap aggregation**, không phải một nhóm đơn lẻ — thực thi tốt nhất trên V2 / V3 / Stable chính là toàn bộ giá trị cốt lõi ("giá tốt nhất giành được tip").
* **Giao nguyên tử cho Client** bằng cách đặt `recipient` của router là địa chỉ Client; không bao giờ làm theo hai bước "hoán đổi về chính mình, rồi chuyển".
* **Độ mới của báo giá** — giá on-chain thay đổi giữa lúc tìm thấy Job và lúc thanh toán; báo giá lại khi thực thi (rào chắn §3).
* **`minOut` tính theo đơn vị thô.** Với các token **scaled-UI / ERC-8056** (Binance Stock Tokens / cổ phiếu RWA), đơn vị thô ≠ giá trị hiển thị; xử lý sai sẽ giao sai mà không có cảnh báo. **Loại trừ các token scaled-UI khỏi v1** cho đến khi đội kỹ thuật xác nhận việc xử lý đơn vị thô end-to-end.
* **Mức trượt giá tối thiểu** của lần hoán đổi thanh toán phải được tính sao cho lượng _được giao_ ≥ `minOut`, có tính đến việc chia tip/phí.

***

### 6. Hành vi khi lỗi & khôi phục

* **Báo giá không đạt `minOut` khi thực thi** → hủy trước/nguyên tử cùng với việc rút từ escrow; Job vẫn ở trạng thái Funded cho Provider khác. Không có trạng thái một phần.
* **Đã ở trạng thái Submitted/Terminal** → bỏ qua (idempotent).
* **Tx thanh toán bị revert** → Job vẫn có thể được người khác nhận; agent ghi lại lỗi và chuyển sang việc khác.
* **Lỗi lặp lại trên một Job** → đưa Job đó vào danh sách đen cục bộ và cảnh báo, thay vì thử lại liên tục.

***

### 7. Các điểm tích hợp (phần BNB / ERC-8183)

Các phần này do BNB Agent Studio / BNBAgent SDK cung cấp, không phải PancakeSwap xây dựng — nhưng đặc tả phụ thuộc vào chúng:

* **Vòng đời Job** (tìm Open → nhận Funded → Submitted → claim) qua BNBAgent SDK.
* **Danh tính Provider** qua ERC-8004.
* **Escrow + chi trả** qua ERC-8183 escrow / x402.
* **Evaluator** — điều kiện phải là "số dư token-B của Client tăng thêm ≥ `minOut`." Xác nhận với BNB **ai vận hành Evaluator** (trung lập/giao thức so với Client) và điều kiện đó có thể được thực thi on-chain.

***

### 8. Lập trường v1 được khuyến nghị & các quyết định còn bỏ ngỏ

1. **Chỉ rút từ escrow, một Job tại một thời điểm, chỉ dùng danh sách token an toàn, không có token scaled-UI.** Bề mặt an toàn nhỏ nhất để giới thiệu khi ra mắt.
2. **Xác nhận giao diện hoán đổi PancakeSwap** — **Aggregator (`aggr`) HTTP API** hay **Smart Router SDK**. Ghi chú của Jerry nói "dùng pcs aggr api"; cần xác nhận agent gọi cái nào, vì nó thay đổi cách tích hợp (và liệu hướng dẫn có cần một phần về aggregation hay không).
3. **Xác nhận cơ chế escrow** với BNB — Provider có thể rút khoản đầu vào đã ký quỹ của Client để định tuyến hoán đổi không, và việc giao cho Client có thể được thực thi như một sản phẩm giao không?
4. **Xác nhận chủ sở hữu Evaluator và điều kiện** (§7).

> Kỹ thuật phê duyệt trước khi giới thiệu: định tuyến rút từ escrow → hoán đổi → giao cho Client một cách nguyên tử; báo giá lại khi thực thi; phép tính `minOut` sau trượt giá; thực thi danh sách an toàn; xử lý Job idempotent.
