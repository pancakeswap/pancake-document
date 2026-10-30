---
description: Pancake Github에서 길 찾기
---

# 코드베이스 개요

## 소개

모든 저장소는 [Github](https://github.com/pancakeswap)에 저장되어 있습니다. 대부분 공개되어 있으며 자유롭게 이슈나 풀 리퀘스트를 제출할 수 있습니다. 먼저 이 가이드 전체와 각 저장소별 가이드라인을 반드시 읽어 주세요.

## Github 저장소

* 프론트엔드: 메인 프론트엔드입니다. 아래에 나열되지 않은 모든 기능을 포함합니다.
  * [sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk) - PancakeSwap 기반으로 애플리케이션을 구축하기 위한 SDK
  * [aptos-swap-sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/aptos-swap-sdk) - Swap SDK의 Aptos 버전
  * [swap-sdk-core](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk-core) - Swap SDK 공용 코드
  * [wagmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/wagmi) - bsc 체인과 binance 지갑 커넥터를 포함한 [wagmi](https://github.com/wagmi-dev/wagmi) 확장
  * [awgmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/awgmi) - wagmi와 유사한 React 훅으로 Aptos에 연결합니다. 지갑 어댑터를 포함합니다.
* 스마트 컨트랙트: BSC와 ETH에 배포된 모든 스마트 컨트랙트입니다.
* 스마트 컨트랙트: Aptos에 배포된 Move 버전의 모든 스마트 컨트랙트입니다.
* 서브그래프: 이벤트와 엔티티를 조회하기 위한 GraphQL 엔드포인트입니다.

<table><thead><tr><th width="227">프로젝트</th><th>Github</th><th data-hidden>웹사이트</th></tr></thead><tbody><tr><td>프론트엔드 모노레포</td><td><a href="https://github.com/pancakeswap/pancake-frontend">https://github.com/pancakeswap/pancake-frontend</a></td><td><a href="https://pancakeswap.finance">🔗PancakeSwap</a></td></tr><tr><td>스마트 컨트랙트</td><td><a href="https://github.com/pancakeswap/pancake-smart-contracts">https://github.com/pancakeswap/pancake-smart-contracts</a></td><td></td></tr><tr><td>스마트 컨트랙트 Move</td><td><a href="https://github.com/pancakeswap/pancake-contracts-move">https://github.com/pancakeswap/pancake-contracts-move</a></td><td></td></tr><tr><td>서브그래프</td><td><a href="https://github.com/pancakeswap/pancake-subgraph">https://github.com/pancakeswap/pancake-subgraph</a></td><td></td></tr></tbody></table>
