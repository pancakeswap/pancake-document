# 📈 분석 (정보 페이지)

## Info 페이지

PancakeSwap 자체 분석 사이트는 여기에서 확인하실 수 있습니다: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

모든 핵심 지표 데이터는 PCS 내부 인덱서에서 가져오며, 인덱서는 컨트랙트가 호출될 때 발생하는 이벤트에서 데이터를 수집합니다.

PancakeSwap 내부 인덱서의 날짜 기준은 일별 통계에 국제 표준시(UTC)를 사용합니다. 따라서 대시보드의 가로축에 표시되는 날짜는 국제 표준시(UTC) 기준 날짜입니다.<br>

## 핵심 지표

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**거래량 (Volume):** 각 거래 페어의 일별 데이터와 각 토큰의 일별 거래 데이터를 모니터링합니다. 일일 거래량은 해당 일의 토큰별 거래량에 가격을 곱하여 산출합니다.

**총 예치 자산 (Total Value Locked):** 내부 인덱서에서 모든 풀을 가져와 각 풀의 reserve\_usd 또는 total\_value\_locked\_usd 값을 읽어옵니다.

**가격 (Price):** PCS 내부 인덱서에서는 여러 기준 풀을 활용하여 USD 관련 가격을 계산합니다. 주요 풀은 스테이블코인 거래 풀이며, 거래량이 가장 높은 거래 풀을 기준 풀로 삼아 거래량 가중치를 기반으로 스테이블코인의 USD 가격을 계산합니다. 또한 기준 토큰과 해당 체인의 스테이블코인 간 거래 풀도 기준 풀로 간주되어 USD 가격을 제공합니다.

_화이트리스트에 등록되지 않았거나 화이트리스트 토큰과 페어를 이루지 않은 토큰은 이 계산에서 제외됩니다._

<br>
