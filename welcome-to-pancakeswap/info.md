# 📈 アナリティクス（Infoページ）

## Infoページ

PancakeSwapのネイティブアナリティクスサイトはこちらでご確認ください：[https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

すべてのコアメトリクスデータはPCS内部インデクサーから取得されており、内部インデクサーはコントラクトが呼び出された際にトリガーされるイベントからデータを収集しています。

PancakeSwapの内部インデクサーにおける日付の次元については、日次統計に国際標準時（UTC）を使用しています。そのため、ダッシュボードの横軸に表示される日付は国際標準時（UTC）での日付を表しています。<br>

## コアメトリクス

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume（取引量）：** 各取引ペアの日次データと各トークンの日次取引データを監視しています。日次取引量は、その日の各トークンの取引量にその価格を掛けることで算出されます。

**Total Value Locked：** 内部インデクサーからすべてのプールを取得し、各プールのreserve_usdまたはtotal_value_locked_usdを読み取ります。

**Price（価格）：** PCS内部インデクサーでは、USD関連の価格計算に複数のベースプールを使用しています。主なプールはステーブルコイン取引プールで、最も取引量が多いプールをベースプールとして使用し、取引量の加重に基づいてステーブルコインのUSD価格を算出します。また、チェーンのステーブルコインに対するベーストークンの取引プールもUSD価格を提供するベースプールとして考慮されます。

_ホワイトリストに登録されていないトークン、またはホワイトリストに登録されたトークンとペアになっていないトークンはこれらの計算から除外されます。_

<br>
