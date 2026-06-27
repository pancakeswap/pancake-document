# Phí Mua & Bán ALP

## Phí mua:

Thông Số Cơ Bản 1: FeeBasisPoints, USDT hiện đang được đặt ở mức 0.25%

Thông Số Cơ Bản 2: TaxBasisPoints, USDT hiện đang được đặt ở mức 0.05%

Giá trị tài sản hiện tại: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Giá trị tài sản hiện tại sau khi đúc: AfterMinValue=InitialValue+MinValue

Tính giá trị tài sản theo trọng số mục tiêu: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight，Total Value=sum(InitialValue)



Giá trị tài sản hiện tại và giá trị mục tiêu (giá trị tuyệt đối): InitialDiff=InitialValue-TargetValue

Sau khi đúc, giá trị tài sản và cơ chế mục tiêu (giá trị tuyệt đối): AfterDiff=AfterMintValue-TargetValue

* nếu AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* nếu AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Phí bán:

Thông Số Cơ Bản 1: FeeBasisPoints, USDT hiện đang được đặt ở mức 0.25%

Thông Số Tỷ Lệ Cơ Bản Tối Đa 2: TaxBasisPoints, USDT hiện đang được đặt ở mức 0.05%

Giá trị tài sản hiện tại: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Giá trị tài sản hiện tại sau khi Đốt: AfterMaxValue=InitialValue-MinValue

Tính giá trị tài sản theo trọng số mục tiêu: TargetValue=Total Value\*Target weight



Giá trị tài sản hiện tại và giá trị mục tiêu (giá trị tuyệt đối): InitialDiff=InitialValue-TargetValue



Sau khi Đốt, giá trị tài sản và cơ chế mục tiêu (giá trị tuyệt đối): AfterMaxDiff=AfterBurnValue-TargetValue

* nếu AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* nếu AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Ví dụ:

Nếu giá trị pool ALP là $10.000.000, PnL chưa thực hiện là $+10.000, giá trị BTC trong pool thanh khoản là $1.000;

Trọng số mục tiêu BTC là 2%, và trọng số hiện tại là 0.01%. Thông số tỷ lệ cơ bản 1 của BTC là 0.25%, và thông số tỷ lệ cơ bản 2 là 0.45%.

Theo tính toán, tỷ lệ mua ALP bằng 1 BTC tại thời điểm này là 0% = 0 BTC. Phí giao dịch để bán ALP để nhận 1 BTC là 0.7% = 0.007BTC.
