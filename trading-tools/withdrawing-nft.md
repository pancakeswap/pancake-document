# 🧙 Page 1

## Cách rút NFT của bạn khỏi PancakeSwap NFT Marketplace

Các trang của PancakeSwap NFT Marketplace không còn khả dụng, nhưng smart contract của marketplace vẫn đang hoạt động. Nếu bạn đã niêm yết một NFT để bán và nó chưa bao giờ được bán, nó vẫn đang được giữ bởi contract của marketplace. Bạn có thể tự lấy lại bằng cách hủy niêm yết trực tiếp trên BscScan.

Việc này mất vài phút cho mỗi NFT và chỉ tốn một lượng nhỏ BNB làm phí gas.

### Trước khi bắt đầu

Bạn sẽ cần:

* **Cùng ví bạn đã dùng để niêm yết NFT.** Chỉ ví đã tạo niêm yết mới có thể hủy nó.
* **Một ví trình duyệt** (ví dụ MetaMask, tiện ích mở rộng Trust Wallet, hoặc tiện ích mở rộng Binance Wallet) được đặt ở mạng **BNB Smart Chain**.
* **Một lượng nhỏ BNB** để trả phí gas. Mỗi NFT được rút trong một giao dịch riêng.

Hãy giữ sẵn các địa chỉ sau:

| Mục                        | Địa chỉ                                      |
| -------------------------- | -------------------------------------------- |
| Contract của marketplace   | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Bộ sưu tập Pancake Squad   | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Bộ sưu tập Pancake Bunnies | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Giữ an toàn**
>
> * Chỉ tương tác với contract của marketplace `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Luôn kiểm tra địa chỉ trong URL BscScan.
> * Việc rút NFT của bạn **không bao giờ** yêu cầu gửi BNB hoặc token, và không bao giờ yêu cầu ký phê duyệt (`approve` hoặc `setApprovalForAll`). Nếu một trang web hoặc ai đó yêu cầu bạn làm vậy, đó là lừa đảo.
> * PancakeSwap sẽ không bao giờ nhắn tin riêng cho bạn hoặc hỏi cụm từ khôi phục của bạn.

### Bước 1: Tìm các NFT bạn vẫn đang niêm yết

Với mỗi NFT bạn muốn rút, bạn cần hai thông tin: **địa chỉ bộ sưu tập** và **token ID**.

1. Mở [trang Read Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) của contract marketplace trên BscScan.
2. Tìm và mở rộng **`viewAsksByCollectionAndSeller`**.
3. Điền vào các trường:
   * `collection`: địa chỉ bộ sưu tập từ bảng ở trên (ví dụ, Pancake Squad là `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: địa chỉ ví của bạn
   * `cursor`: `0`
   * `size`: `100`
4. Nhấp **Query**.
5. Xem kết quả `tokenIds`. Đây là các token ID bạn vẫn đang niêm yết trong bộ sưu tập đó, và là các NFT bạn có thể rút.
6. Nếu bạn đã niêm yết NFT trong nhiều hơn một bộ sưu tập, hãy lặp lại các bước 3 đến 5 cho từng bộ sưu tập.

**Nếu `tokenIds` trống (`[]`)**, bạn không có niêm yết nào đang hoạt động trong bộ sưu tập đó. NFT của bạn đã được bán (trong trường hợp đó bạn đã nhận BNB) hoặc bạn đã hủy niêm yết trước đó (trong trường hợp đó nó đã về lại ví của bạn).

**Nếu bạn có hơn 100 niêm yết** trong một bộ sưu tập, số cuối cùng trong kết quả là cursor tiếp theo. Hãy query lại bằng số đó làm `cursor` để xem phần còn lại.

**Nếu NFT của bạn thuộc bộ sưu tập khác ngoài Pancake Squad hoặc Pancake Bunnies**, hãy mở rộng **`viewCollections`** trên cùng trang, nhập `cursor = 0` và `size = 100`, rồi nhấp **Query** để xem mọi bộ sưu tập mà marketplace hỗ trợ.

### Bước 2: Rút NFT của bạn

1. Mở [trang Write Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) của contract marketplace trên BscScan.
2. Nhấp **Connect to Web3** và kết nối cùng ví đã niêm yết NFT. Đảm bảo ví của bạn đang ở BNB Smart Chain.
3. Tìm và mở rộng **`cancelAskOrder`**.
4. Điền vào các trường:
   * `_collection`: địa chỉ bộ sưu tập từ Bước 1
   * `_tokenId`: token ID từ Bước 1, dưới dạng số thuần (ví dụ `1234`)
5. Nhấp **Write** và xác nhận giao dịch trong ví của bạn. Bạn không gửi BNB nào; bạn chỉ trả phí gas.
6. Khi giao dịch thành công, NFT đã trở lại ví của bạn.
7. Lặp lại cho từng NFT bạn muốn rút.

Để xác nhận đã thành công, hãy chạy lại Bước 1. Token ID sẽ không còn xuất hiện trong danh sách.

### Khắc phục sự cố

| Vấn đề                                                    | Ý nghĩa và cách xử lý                                                                                                                                                                                       |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Lỗi: `Order: Token not listed`                            | Ví đang kết nối đã không niêm yết token ID này trong bộ sưu tập này, hoặc NFT đã được bán hoặc đã rút. Hãy kiểm tra rằng bạn đang dùng ví gốc và đúng địa chỉ bộ sưu tập cùng token ID. |
| Nút Write không phản hồi                                  | Có thể ví của bạn đang ở sai mạng. Hãy chuyển sang BNB Smart Chain và kết nối lại.                                                                                                                          |
| Hết gas hoặc không đủ số dư                               | Hãy thêm một lượng nhỏ BNB vào ví để trả phí gas.                                                                                                                                                           |
| Tôi không còn quyền truy cập vào ví đã niêm yết NFT       | Chỉ ví gốc mới có thể hủy niêm yết. Không ai, kể cả PancakeSwap, có thể rút thay bạn.                                                                                                                       |
