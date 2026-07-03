---
hidden: true
---

# Smart Router（v2）

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwapのSmart Routerは、AMM・StableSwap（BNB Chain）およびAMMとマーケットメーカー（Ethereum）を連携させ、より優れた流動性と価格を提供するルーティングアルゴリズムです。複数のプールをまたいで取引を実行し、トレーダーに最良の価格を見つけるスマートオーダールーティングアルゴリズムを使用しています。StableSwapの詳細については[こちら](/broken/pages/nNPogTZMxocdyFIBYbkE)、マーケットメーカー連携の詳細については[こちら](../market-maker-integration.md)をご参照ください。

PancakeSwap開発チームは、製品のテストと改善をさらに進めるためにStableSwapペアを段階的に展開していきます。

## AMMスワップにSmart Routerを使用すべき理由&#x20;

* 同様の資産価格を持つステーブルコインやその他のペアを、同じ取引ステップでより効率的にスワップできます。
* マーケットメーカーに対してスワップが可能で、通常のPancakeSwap AMMよりも優れた約定が得られる場合があります。
* StableSwap機能を使用することで、通常のAMMよりも取引スリッページが低くなります。
* StableSwapの取引手数料は通常のAMMと比較して低くなっています。

## 開発中の機能&#x20;

* アウトプットのUIを改善予定。
* より効率的な取引のためのスプリットルート。例：取引サイズと流動性に応じて手数料を節約するため、ルーターがペアの50%を別のルートに送ります。&#x20;
