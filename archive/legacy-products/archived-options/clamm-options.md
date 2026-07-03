# CLAMM Options

{% hint style="danger" %}
\[アーカイブ済み] オプション – 2025年3月11日をもって\
まだ引き出していない流動性がある場合は、https://www.stryke.xyz/en/trade にアクセスして直ちに引き出してください。
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Optionsはオンチェーンのオプション取引への革新的なアプローチを提供し、PancakeSwap上のv3流動性を活用するための流動性プロバイダー向けプラットフォームです。これにより、流動性をv3流動性プールとオプション売却の両方に活用でき、標準的なAMM取引手数料、オプションプレミアム、追加報酬を得ながら、トレーダーはこの流動性を使用して様々なトークンのアメリカ型オプションを購入できます。

Stryke（旧Dopex）チームが開発したCLAMM Optionsプロトコルは、オプショントレーダー（購入者）とPancakeSwap v3プールのための効率的なデュアル流動性提供システムを導入しています。

CLAMM Optionsの仕組みについて以下に説明します：

1. CLAMM Optionsに流動性を追加するLPは、選択した価格範囲内で指定されたPancakeSwap v3プールにも同時に貢献します。
2. オプショントレーダー（購入者）がポジションを開始すると、流動性がv3プールから引き出されてオプション売却が促進されます。対応するLPはそれによりオプション売り手となり、プレミアムを受け取ります。
3. オプション購入者が使用しない流動性はPancakeSwap v3プールに残り、取引手数料を得る可能性があります。
4. v3プールでオプションを売却して流動性を提供することのペイオフは、同じ非恒久的損失を反映しており、ユーザーはv3プールに流動性を追加する通常の方法と比較してリスクが増加しません。
5. LPには一部のリスクがあり、オプション購入需要が低いために流動性が使用されない場合があります。さらに、流動性が非アクティブな範囲のプールに追加されるため、手数料を得られない場合があります。

PancakeSwapのアメリカ型CLAMM Optionsは、1時間から24時間の多様な満期期間の柔軟性を提供してArbitrumチェーンでデビューする予定です。

| **マーケット**          | ARB/USDC、ETH/USDC、wBTC/USDC |
| -------------------- | --------------------------------- |
| **オプションタイプ**    | コール＆プット                        |
| **行使価格**    | v3プールのティックに基づく            |
| **満期期間** | 1H、2H、6H、12H、24H          |

**行使条件：** ユーザーはイン・ザ・マネーのオプションが無価値で満期を迎えるのを防ぐために、クローズ前にポジションを行使できます。自動行使を有効にして、満期時に自動的に利益を確定し、追加アクションをスキップすることができます。

### ステップバイステップガイド

PancakeSwap CLAMM Optionsの使い方についてのステップバイステップガイドです。

**トレーダー向け：** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**LP向け：** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
