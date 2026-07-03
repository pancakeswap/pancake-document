# Biaya Pembelian & Penjualan ALP

## Biaya pembelian:

Parameter Tingkat Dasar 1: FeeBasisPoints, USDT saat ini ditetapkan pada 0,25%

Parameter Tingkat Dasar 2: TaxBasisPoints, USDT saat ini ditetapkan pada 0,05%

Nilai aset saat ini: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Nilai aset saat ini setelah pencetakan: AfterMinValue=InitialValue+MinValue

Hitung nilai Aset sesuai bobot target: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Bobot Target, Total Value=sum(InitialValue)



Nilai Aset saat ini dan nilai target (nilai absolut): InitialDiff=InitialValue-TargetValue

Setelah Pencetakan, nilai aset dan mekanisme target (nilai absolut): AfterDiff=AfterMintValue-TargetValue

* jika AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* jika AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Biaya penjualan:

Parameter Tingkat Dasar 1: FeeBasisPoints, USDT saat ini ditetapkan pada 0,25%

Parameter Tingkat Dasar Maks 2: TaxBasisPoints, USDT saat ini ditetapkan pada 0,05%

Nilai aset saat ini: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Nilai aset saat ini setelah Burn: AfterMaxValue=InitialValue-MinValue

Menghitung nilai Aset sesuai bobot target: TargetValue=Total Value\*Bobot Target



Nilai aset saat ini dan nilai target (nilai absolut): InitialDiff=InitialValue-TargetValue



Setelah Burn, nilai aset dan mekanisme target (nilai absolut): AfterMaxDiff=AfterBurnValue-TargetValue

* jika AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* jika AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Sebagai contoh:

Jika nilai pool ALP adalah $10.000.000, PnL yang belum terealisasi adalah $+10.000, nilai BTC dalam pool likuiditas adalah $1.000;

Bobot target BTC adalah 2%, dan bobot saat ini adalah 0,01%. Parameter tingkat dasar 1 BTC adalah 0,25%, dan parameter tingkat dasar 2 adalah 0,45%.

Berdasarkan perhitungan, tingkat pembelian ALP dengan 1 BTC saat ini adalah 0% = 0 BTC. Biaya transaksi untuk menjual ALP untuk mendapatkan 1 BTC adalah 0,7% = 0,007BTC.

