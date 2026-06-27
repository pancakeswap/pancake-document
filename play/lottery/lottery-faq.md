# FAQ Xổ số

## Nếu không có người thắng thì sao?

Nếu CAKE trong quỹ thưởng không được thắng, nó sẽ không bị lãng phí! CAKE chưa được nhận sẽ được chuyển sang vòng Xổ số tiếp theo.

## Vé của tôi khớp nhiều số nhưng tôi không thể nhận giải thưởng

Vé chỉ đủ điều kiện nhận giải thưởng khi các số khớp từ trái sang phải. Xem [tài liệu Lottery v2](./) để có giải thích chi tiết.

## Lottery v2 khác Lottery v1 như thế nào?

Lottery v2 phân bổ giải thưởng rộng rãi hơn Lottery v1. Lottery v2 cho mỗi vé cơ hội 1/10 để khớp số đầu tiên, nghĩa là nhiều vé hơn sẽ ít nhất thắng một phần thưởng nhỏ. Ngoài ra còn có 6 số (tăng từ 4) cần khớp theo thứ tự để giành giải lớn nhất.

Nhìn chung, điều này có nghĩa là nhiều vé hơn có thể thắng giải, nhưng jackpot lớn nhất sẽ được trúng ít thường xuyên hơn, tạo ra các quỹ giải thưởng hàng đầu khổng lồ!

**Lottery v2 giới thiệu:**

* giá vé rẻ hơn (\~$5 USD tính bằng CAKE mỗi vé) không dao động mạnh theo giá CAKE
* chiết khấu khi mua số lượng lớn
* 6 hạng quỹ giải thưởng với phần thưởng tăng dần khi khớp nhiều số hơn
* chọn số thủ công (tùy chọn), để người dùng có thể dùng số may mắn của mình
* [VRF của Chainlink](https://docs.chain.link/docs/chainlink-vrf/) để đảm bảo tính ngẫu nhiên thực sự và bảo mật
* phí tổng thể thấp hơn (xem [phần bên dưới trang này](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) để biết thêm thông tin)

[Tìm hiểu thêm về tính năng, cách chơi và giải thưởng của Lottery v2](./)

## Giải thưởng được phân bổ giữa các hạng như thế nào?

Quỹ giải thưởng của mỗi hạng là một phần của tổng CAKE trong mỗi vòng Xổ số.

* | Hạng (số khớp theo thứ tự) | Phân bổ CAKE |
  | -------------------------- | ------------ |
  | 1 số đầu tiên              | 2%           |
  | 2 số đầu tiên              | 3%           |
  | 3 số đầu tiên              | 5%           |
  | 4 số đầu tiên              | 10%          |
  | 5 số đầu tiên              | 20%          |
  | 6 số đầu tiên              | 40%          |
  | Đốt                        | 20%          |

## Tôi có thể hoán đổi vé của mình trở lại thành CAKE không?

Không, sau khi đã mua bạn sẽ không thể chuyển đổi vé của mình trở lại thành CAKE.

## Nếu thắng, tôi có cần nhận thưởng thủ công không?

Có, bạn sẽ cần nhấp vào nút **Check Now** trong mục "Are you a winner?" trên trang Xổ số.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## Tần suất xổ số là bao lâu?

Một lần quay số xổ số diễn ra mỗi 12 hoặc 36 giờ. Mỗi ngày có một lần quay số xổ số luân phiên giữa 0 giờ sáng UTC và 12 giờ trưa UTC, các vòng tiếp theo sau vòng 0 giờ sáng UTC sẽ là sau 36 giờ, các vòng tiếp theo sau vòng 12 giờ trưa UTC sẽ là sau 12 giờ.

![Lottery injection schedule](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## Tôi sẽ phải trả phí giao dịch bao nhiêu khi mua vé?

Mỗi lần mua vé là một giao dịch. Mua một vé trong một lần mua sẽ tốn phí giao dịch thông thường.

Tuy nhiên, mua nhiều vé hơn trong lần mua đó sẽ tăng phí. Mua 100 vé thay vì 1 vé sẽ không nhân phí lên 100 lần, nhưng có thể tăng phí khoảng 5-6 lần (mặc dù điều này có thể khác nhau).

## Chiết khấu mua số lượng lớn hoạt động như thế nào?

Chiết khấu mua số lượng lớn thưởng cho việc mua nhiều vé hơn với mức chiết khấu tăng dần. Nếu bạn chỉ mua 2 vé, mức chiết khấu không đáng kể, nhưng sẽ tăng nhanh khi bạn tăng số lượng vé mua trong một giao dịch.

Chiết khấu chỉ áp dụng cho từng giao dịch tối đa 100 vé. Chiết khấu không chuyển sang giao dịch tiếp theo hay vòng tiếp theo.

## Tại sao tôi chỉ có thể mua 100 vé?

Bạn chỉ có thể mua tối đa 100 vé trong một lần mua, nhưng bạn có thể thực hiện nhiều lần mua. Không có gì ngăn bạn mua thêm vé sau 100 vé đầu tiên.

## Nếu tôi tự tạo hai hay nhiều vé có cùng số và chúng thắng, tôi có đủ điều kiện nhận giải cho từng vé không?

Có, mỗi vé được coi là một lần tham gia riêng biệt vào Xổ số. Tuy nhiên, hãy lưu ý rằng giải thưởng sẽ không theo tỷ lệ 1:1, vì mỗi vé thắng của bạn sẽ làm giảm phần của từng vé trong tổng giải thưởng của hạng.

## Lịch bổ sung: CAKE được thêm vào Xổ số khi nào?

Khi mọi người mua vé, CAKE họ chi tiêu được thêm vào quỹ xổ số. Ngoài ra, 8.000 CAKE cũng được thêm vào (bổ sung) quỹ xổ số mỗi vòng cách nhau theo lịch đều đặn trong suốt bảy vòng mỗi tuần như thể hiện trong hình lịch xổ số ở trên.
