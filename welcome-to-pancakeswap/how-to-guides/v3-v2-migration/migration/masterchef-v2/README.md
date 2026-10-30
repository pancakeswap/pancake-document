---
description: MasterChef v2로 마이그레이션하기
---

# MasterChef v2

PancakeSwap MasterChef v2는 파밍을 위한 새로운 메인 스테이킹 컨트랙트로, CAKE 풀, 소각 및 기타 PancakeSwap 상품을 포함한 $CAKE 배출량을 더욱 유연하게 조정할 수 있습니다.

### 마이그레이션이 필요한가요?

현재 PancakeSwap MasterChef([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E))를 사용 중이라면 새로운 컨트랙트([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652))로 마이그레이션해야 합니다.

### 개요

#### 예치&#x20;

현재 PancakeSwap MasterChef에서 `enterStaking(uint256 _amount)`를 사용 중이라면 새로운 CAKE 풀 컨트랙트로 마이그레이션해야 합니다. 관련 문서는 [여기](../cake-syrup-pool.md)에서 확인하세요.

파밍 풀의 예치 함수는 변경되지 않았습니다. 다만 MasterChef 주소와 `pid`를 업그레이드해야 하며, MasterChef v2의 새로운 `pids` 목록은 [파밍 목록](list-of-farms.md)에서 확인하세요.

#### 풀 유형

MasterChef v2에는 일반 파밍 풀과 특수 파밍 풀의 두 가지 유형의 풀이 있으며, `poolInfo(_pid).isRegular`를 사용하여 풀 유형을 조회할 수 있습니다. 두 유형은 서로 다른 `totalAllocPoint`를 공유하므로 독립적인 두 개의 풀 집합으로 운영됩니다.

특수 파밍 풀: 화이트리스트에 등록된 주소만 예치할 수 있습니다. 주로 PancakeSwap 내부 상품에서 보상을 분배하는 데 사용됩니다.

일반 파밍 풀: 일반적인 LP 토큰 파밍입니다. 예를 들어 CAKE-BNB, BNB-BUSD 등이 있습니다.

#### 출금

현재 PancakeSwap MasterChef에서 `leaveStaking(uint256 _amount)`를 사용 중이라면 새로운 CAKE 풀 컨트랙트로 마이그레이션해야 합니다. 관련 문서는 [여기](../cake-syrup-pool.md)에서 확인하세요.

파밍 풀의 출금 함수는 변경되지 않았습니다. 다만 MasterChef 주소와 `pid`를 업데이트해야 하며, MasterChef v2의 새로운 `pids` 목록은 [파밍 목록](list-of-farms.md)에서 확인하세요.

#### 스테이킹 잔액

`userInfo[_pid][_user].amount`를 사용하여 스테이킹 잔액을 조회하세요.

#### 스테이킹 토큰&#x20;

새로운 `PoolInfo` 구조체에는 LP 토큰 주소 필드가 **포함되어 있지 않으므로**, 특정 풀의 스테이킹 토큰을 조회하려면 `lpToken(_pid)`를 사용해야 합니다.&#x20;

#### 총 스테이킹 지분/수량

`lpToken.balanceOf(MasterChef.address)`를 사용하여 특정 파밍 풀의 총 스테이킹 수량을 확인하세요.

다만 MasterChef v2에서는 사용자의 지분이 부스트될 수 있습니다. 따라서 보상은 `PoolInfo`의 새로운 `totalBoostedShare` 필드를 각 풀의 총 지분으로 사용하여 계산됩니다. 예를 들어 풀 0에 사용자가 2명 있고, user1이 LP 100개를 스테이킹하고(부스트 없음), user2가 100개를 스테이킹하며(`boostMultiplier`가 1.05인 경우), `totalBoostedShare`는 205가 됩니다. 그 결과 user2가 더 많은 보상을 받게 됩니다.

#### CakePerBlock

`cakePerBlock(bool _isRegular)`를 사용하여 모든 PancakeSwap 파밍에 배분되는 블록당 CAKE 보상을 조회할 수 있습니다.

### 메인넷 컨트랙트 주소

**컨트랙트 이름:** MasterChef v2\
**컨트랙트 주소:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[BscScan에서 PancakeSwap: Main Staking Contract v2 보기.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### 테스트넷 환경

다음 테스트넷 환경을 사용하여 프로젝트와 새로운 PancakeSwap MasterChef v2의 연동을 테스트할 수 있습니다. 궁금한 점이 있다면 기존 채널을 통해 팀에 문의하거나 bun@pancakeswap.com으로 이메일을 보내주세요.

**더미 토큰:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (`mint(address _to, uint256 _amount) public`를 사용하여 민팅 가능)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (`mint(uint256 amount) public`를 사용하여 민팅 가능)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### 팩토리 및 라우터

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP 페어

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChef 목록

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`

