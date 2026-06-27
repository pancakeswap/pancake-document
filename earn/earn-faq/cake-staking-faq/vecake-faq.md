---
hidden: true
---

# FAQ về veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Sự khác biệt giữa CAKE bị khóa và veCAKE là gì? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE là phiên bản mới của fixed-term CAKE staking với nhiều lợi ích và quyền lực hơn cho những người giữ CAKE bị khóa. Bao gồm bỏ phiếu trọng số gauge, ưu đãi thêm, tăng cường lợi suất và nhiều hơn nữa.

#### Điều gì xảy ra với phần thưởng CAKE pool khi veCAKE mới được triển khai <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

Emissions phần thưởng CAKE pool sẽ được chuyển hướng để thưởng cho tất cả những người giữ veCAKE theo số dư veCAKE của họ so với tổng cung.

Phần thưởng CAKE và phần thưởng chia sẻ doanh thu hàng tuần giờ đây có thể được nhận hàng tuần vào thứ Năm.

Lưu ý rằng để tiếp tục nhận phần thưởng, người dùng sẽ cần chuyển sang veCAKE staking mới.

#### Thời gian tối đa tôi có thể khóa CAKE là bao lâu <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

Thời gian tối đa bạn có thể khóa CAKE hiện đã được mở rộng lên 4 năm.

#### veCAKE có phải là token mới không? Nó có thể chuyển nhượng không? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE là một con số được tạo ra trực tiếp dựa trên số lượng CAKE bị khóa và thời gian khóa còn lại. Nó không phải là token tiêu chuẩn và không thể chuyển nhượng.

#### Tại sao số dư veCAKE của tôi thay đổi? Làm thế nào để tính số dư? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

Số dư veCAKE giảm tuyến tính về 0 dựa trên thời gian khóa còn lại. Do đó khi chúng ta đang tiến gần đến thời điểm mở khóa, số dư của bạn giảm.

Số dư veCAKE có thể được tính bằng:

```javascript
lockedAmount // số lượng CAKE bị khóa
currentTime // thời gian hiện tại
lockEndTime // thời gian mở khóa
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // thời gian khóa tối đa (4 năm)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### Làm thế nào để tăng veCAKE của tôi? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Khi bạn có vị thế veCAKE đang hoạt động, bạn có thể thêm CAKE hoặc gia hạn/mở rộng thời gian khóa để tăng số dư veCAKE.

#### Điều gì xảy ra khi vị thế mở khóa? Tôi có thể gia hạn ngay không? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Khi vị thế veCAKE staking được mở khóa, bạn có thể rút tất cả CAKE đã stake.

Để gia hạn vị thế, bạn cần rút tất cả CAKE và thiết lập vị thế staking mới bằng cách chọn số lượng cần khóa và thời gian khóa.

#### Tôi đã khóa trong 1 tuần, tại sao thời gian khóa còn lại ít hơn 1 tuần? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Khi bạn khóa với veCAKE mới, thời gian mở khóa được làm tròn về phía trước đến thứ Năm gần nhất với giờ UTC. Ví dụ: khi bạn khóa trong 1 tuần vào thứ Ba, thời gian mở khóa thực tế của bạn sẽ là thứ Năm sắp tới, tức là 2 ngày sau.

Bạn có thể xem trước thời gian mở khóa thực tế ở phía dưới.

#### Tôi có thể khóa thêm CAKE trong CAKE pool không? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

Không.

Khi veCAKE được triển khai, CAKE staking pool sẽ bị ngừng sử dụng và không còn chấp nhận bất kỳ gia hạn hoặc tiền nạp CAKE nào nữa.

Để khóa CAKE và tận hưởng các lợi ích, hãy truy cập trang veCAKE.

#### Tại sao tôi không thể chuyển đổi? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

Chuyển đổi từ CAKE pool sang veCAKE yêu cầu bạn phải có vị thế đang hoạt động. Nếu vị thế staking CAKE pool của bạn đã được mở khóa, chỉ cần rút CAKE đó và tạo vị thế veCAKE staking gốc.

Trong một số trường hợp, không thể thực hiện chuyển đổi khi thời gian khóa CAKE pool còn lại ít hơn 7 ngày. Trong trường hợp đó, chỉ cần đợi mở khóa, rút CAKE đó và tạo vị thế veCAKE staking gốc.

#### Tôi có thể rút CAKE bị khóa sớm không? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

Không.

Khi bị khóa, CAKE sẽ được stake trong hợp đồng veCAKE cho đến thời điểm mở khóa.

#### Tôi có thể chuyển đổi một phần CAKE không? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

Không.

Bạn chỉ có thể chuyển đổi toàn bộ vị thế CAKE pool của mình cùng một lúc.

#### Điều gì sẽ xảy ra với iCAKE, bCAKE, vCAKE và rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Đối với iCAKE:**

IFO iCAKE đã được nâng cấp để hỗ trợ veCAKE. Xem:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Đối với bCAKE:**

Farm boosting bCAKE đã được nâng cấp để hỗ trợ veCAKE. Xem:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Đối với vCAKE:**

Bỏ phiếu vCAKE đã được nâng cấp để hỗ trợ veCAKE. Xem:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Đối với rCAKE:**

Tất cả những người giữ veCAKE (gốc hoặc đã chuyển đổi) sẽ tự động được đăng ký vào pool chia sẻ doanh thu mới. Cổ phần doanh thu được phân phối theo lịch trình hiện có. Pool chia sẻ doanh thu cũ sẽ bị ngừng hoạt động, người dùng có thể nhận phần thưởng đang chờ xử lý bằng cách đến thẻ lợi ích. Xem:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### Ví multisig có thể được sử dụng để tương tác với veCAKE không?

Có

Tuy nhiên, đã có modifier `noContract` được triển khai trong hợp đồng veCAKE staking cho các địa chỉ không có trong danh sách trắng. Để cho phép staking hoặc chuyển đổi từ CAKE staking pool fixed-term. Tất cả ví multisig dựa trên hợp đồng phải thực hiện hành động tự đưa vào danh sách trắng một lần.

Để đưa vào danh sách trắng, hãy truy cập một trong các trang sau:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Một lời nhắc sẽ xuất hiện. Nhấp "Whitelist" và tiến hành tx trong ví multisig của bạn.

Một tx sẽ được gửi đến chủ sở hữu của veCAKE, đây là hợp đồng với hàm ghi không cần quyền để cho phép bất kỳ hợp đồng nào tự đưa vào danh sách trắng.

Nếu lời nhắc không xuất hiện, hãy làm theo hướng dẫn này để thực thi tx từ [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11):

```
// gọi:
VECakeOwner.setWhitelist(bool _status = true)

// Địa chỉ VECakeOwner:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Tại sao có nhiều APR?

Khóa CAKE để nhận veCAKE cung cấp một số lợi ích tuyệt vời xung quanh bộ sản phẩm được xây dựng bởi PancakeSwap. Các lợi ích và ưu đãi đến dưới nhiều hình thức và từ các nguồn khác nhau. Do đó, có nhiều APR.

Bạn có thể kiếm tất cả chúng đồng thời, do đó APR kết hợp sẽ là tổng của tất cả các APR.

Lưu ý rằng nhiều lợi ích khác từ veCAKE không thể được định lượng theo định dạng APR, chẳng hạn như [Farm Yield Booster bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) hoặc [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). Hãy chắc chắn xem những cái đó nữa.

#### APR Pool veCAKE là gì?

Đây là ưu đãi đến từ CAKE emissions, với tỷ lệ được kiểm soát bởi gauge bỏ phiếu veCAKE Pool.

Để tăng emission cho gauge này, hãy xem [Gauge Voting](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### APR Chia sẻ doanh thu là gì?

Đây là ưu đãi đến từ chia sẻ doanh thu giao thức, đến từ phí hoán đổi thu được trong các sản phẩm DEX.

Xem [Revenue Sharing](/broken/pages/wQegezs7c6A2HzQjPEjh) để biết thêm thông tin.
