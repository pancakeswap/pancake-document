---
description: PancakeSwapのGithubを活用しましょう
---

# コードベース概要

## はじめに

すべてのリポジトリは[Github](https://github.com/pancakeswap)に保存されています。ほとんどは公開されており、Issueやプルリクエストを自由に提出できます。始める前に、このガイド全体と各リポジトリ固有のガイドラインをよく読んでください。

## Githubリポジトリ

* フロントエンド：メインのフロントエンド。以下にリストされていない機能がすべて含まれています。
  * [sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk) - PancakeSwap上でアプリケーションを構築するためのSDK
  * [aptos-swap-sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/aptos-swap-sdk) - Swap SDKのAptosバージョン
  * [swap-sdk-core](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk-core) - Swap SDKの共有コード
  * [wagmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/wagmi) - [wagmi](https://github.com/wagmi-dev/wagmi)の拡張機能。BSCチェーンとBinanceウォレットコネクターを含む
  * [awgmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/awgmi) - 同様のwagmi React hooksでAptosに接続。ウォレットアダプターを含む
* スマートコントラクト：BSCとETHにデプロイされたすべてのスマートコントラクト。
* スマートコントラクト：AptosにデプロイされたすべてのスマートコントラクトのMoveバージョン。
* Subgraph：イベントとエンティティをクエリするためのGraphQLエンドポイント。



<table><thead><tr><th width="227">プロジェクト</th><th>Github</th><th data-hidden>ウェブサイト</th></tr></thead><tbody><tr><td>Frontend Monorepo</td><td><a href="https://github.com/pancakeswap/pancake-frontend">https://github.com/pancakeswap/pancake-frontend</a></td><td><a href="https://pancakeswap.finance">🔗PancakeSwap</a></td></tr><tr><td>Smart Contract</td><td><a href="https://github.com/pancakeswap/pancake-smart-contracts">https://github.com/pancakeswap/pancake-smart-contracts</a></td><td></td></tr><tr><td>Smart Contract Move</td><td><a href="https://github.com/pancakeswap/pancake-contracts-move">https://github.com/pancakeswap/pancake-contracts-move</a></td><td></td></tr><tr><td>Subgraph</td><td><a href="https://github.com/pancakeswap/pancake-subgraph">https://github.com/pancakeswap/pancake-subgraph </a></td><td></td></tr></tbody></table>
