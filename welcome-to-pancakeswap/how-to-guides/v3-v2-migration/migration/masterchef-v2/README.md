---
description: MasterChef v2に移行する
---

# MasterChef v2

PancakeSwap MasterChef v2は、Farmの新しいメインステーキングコントラクトで、CAKE Pool、バーン、その他のPancakeSwap製品を含む$CAKE排出量の調整に高い柔軟性を提供します。

### マイグレーションは必要ですか？

現在PancakeSwap MasterChef（[0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)）を使用している場合は、新しいコントラクト（[0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)）に移行する必要があります。

### 概要

#### 入金&#x20;

現在PancakeSwap MasterChefで`enterStaking(uint256 _amount)`を使用している場合は、新しいCAKE Poolコントラクトに移行する必要があります。関連ドキュメントは[こちら](../cake-syrup-pool.md)をご確認ください。

ファームプールの入金関数は変わりません。ただし、MasterChefのアドレスと`pid`を更新する必要があります。MasterChef v2の新しい`pid`のリストは[ファームリスト](list-of-farms.md)でご確認ください。

#### プールの種類

MasterChef v2には2種類のプールがあります。通常のファームプールと特別なファームプールで、`poolInfo(_pid).isRegular`を使用してプールの種類を照会できます。それぞれ異なる`totalAllocPoint`を持ち、2つの独立したプールセットを構成しています。

特別なファームプール：ホワイトリストに登録されたアドレスのみが入金できます。通常、報酬配分のためにPancakeSwap内部製品で使用されます。

通常のファームプール：通常のLPトークンファームです。例：CAKE-BNB、BNB-BUSDなど。

#### 出金

現在PancakeSwap MasterChefで`leaveStaking(uint256 _amount)`を使用している場合は、新しいCAKE Poolコントラクトに移行する必要があります。関連ドキュメントは[こちら](../cake-syrup-pool.md)をご確認ください。

ファームプールの出金関数は変わりません。ただし、MasterChefのアドレスと`pid`を更新する必要があります。MasterChef v2の新しい`pid`のリストは[ファームリスト](list-of-farms.md)でご確認ください。

#### ステーキング残高

`userInfo[_pid][_user].amount`を使用してステーキング残高を照会できます。

#### ステーキングトークン&#x20;

新しい`PoolInfo`構造体にはLPトークンアドレスフィールドが**含まれていない**ことにご注意ください。任意のプールのステーキングトークンを照会するには`lpToken(_pid)`を使用する必要があります。&#x20;

#### 合計ステーキングシェア/金額

任意のファームプールの合計ステーキング量を取得するには`lpToken.balanceOf(MasterChef.address)`を使用します。

ただし、MasterChef v2ではユーザーのシェアをブーストできます（近日公開予定）。そのため、報酬は各プールの合計シェアとして`PoolInfo`の新しい`totalBoostedShare`フィールドを使用して計算されます。例えば、プール0に2人のユーザーがいて、user1が100 LPをステーキング（ブーストなし）、user2が100 LPをステーキング（`boostMultiplier`が1.05）の場合、`totalBoostedShare`は205になります。結果として、user2がより多くの報酬を獲得します。

#### CakePerBlock

`cakePerBlock(bool _isRegular)`を使用して、PancakeSwapの全ファームに対する1ブロックあたりのCAKE報酬を照会できます。

### メインネットコントラクトアドレス

**コントラクト名：** MasterChef v2\
**コントラクトアドレス：** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[BscScanでPancakeSwap: Main Staking Contract v2を確認する。](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### テストネット環境

以下のテストネット環境を使用して、新しいPancakeSwap MasterChef v2とのプロジェクト統合をテストできます。ご質問がある場合は、既存のチャンネルを通じてチームにお問い合わせいただくか、bun@pancakeswap.comにメールでご連絡ください。

**ダミートークン：**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  （`mint(address _to, uint256 _amount) public`を使用してミント可能）
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  （`mint(uint256 amount) public`を使用してミント可能）
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### FactoryとRouter

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LPペア

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
