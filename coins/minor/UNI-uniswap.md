# UNI (Uniswap) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
**이더리움 최대 탈중앙 거래소(DEX) 프로토콜 Uniswap의 거버넌스 토큰** — 2025년 말 "UNIfication" 업그레이드로 프로토콜 수수료가 UNI 소각(바이백&번)에 연결되며 단순 거버넌스 토큰에서 현금흐름 연동 자산으로 전환 중.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **AMM(자동화 시장조성) 엔진 v2/v3/v4** | v2 상수곱 공식, v3 집중유동성(Concentrated Liquidity), v4는 싱글톤 컨트랙트 + **Hooks**(풀별 커스텀 로직 삽입) 구조로 가스비 절감 및 커스터마이징 지원 |
| **Hooks (v4)** | 유동성 풀에 동적 수수료, 온체인 리밸런싱, MEV 보호 로직 등을 플러그인 형태로 추가하는 v4 핵심 기능. 최근 'Permissioned Pools' 표준으로 허가형 RWA 유동성 접근도 지원 |
| **Unichain** | Uniswap Labs가 만든 OP 스택 기반 이더리움 L2. DEX 트레이딩에 최적화된 블록타임/MEV 구조 지향, 시퀀서 수익 일부가 UNI 소각 재원으로 편입 |
| **TokenJar → Firepit** | UNIfication 이후 신설된 파이프라인. 프로토콜 수수료가 TokenJar(징수)에 모였다가 Firepit(소각 주소)으로 전송되는 자동 소각 구조 |

## 3. UNI 토큰의 역할과 구조적 특징 — "UNIfication" 이후 지형 변화
- **최대 발행량 10억 UNI**, 유통량 약 6.23억 개(약 62%), 시총 약 32.5억 달러, FDV 약 46.4억 달러 (2026-09-01 CoinGecko 기준)
- 2025-12-25 거버넌스 투표로 **"UNIfication" 제안 통과**(찬성 1억2,534만 vs 반대 742표라는 압도적 표차), 12-28 실행:
  - **1억 UNI(발행량의 10%) 소각** — 소각 시점 가격($5.96) 기준 약 **5억9,600만 달러 상당** 즉시 소각
  - **수수료 스위치(Fee Switch) 가동**: v2는 기존 0.3% 수수료 중 LP 0.25% + 프로토콜 0.05%로 분할, v3는 풀 변동성에 따라 저수수료 풀 25%·고변동성 풀 16.7%를 프로토콜 수수료로 징수
  - 웹/앱 프론트엔드 수수료는 0%로 인하 — 수익모델을 앱단이 아닌 **프로토콜단**으로 완전히 이전
  - 이더리움·Arbitrum·Base·BNB체인·Polygon·OP메인넷·Robinhood체인 등 7개 체인으로 확대 가동 중이며, Unichain 시퀀서 수익도 L1 비용 차감 후 소각 재원에 합류
  - 8월 중순 기준 누적 소각량 약 1.078억 UNI(약 $2.5억+ 상당), 일일 프로토콜 수익은 7월 초 약 $11.4만에서 v4 수수료 스위치 이후 약 $32.5만로 증가(Bitget News)
- 이 구조 변화로 UNI를 매출 대비 밸류에이션(P/E 유사 모델)으로 평가하려는 시도가 늘고 있음 — 연환산 프로토콜 수수료 약 5억 달러 규모로 추정, 최근 시가총액 대비 배수(P/Fee)는 약 4배 수준
- ⚠️ 다만 연간 약 2,000만 UNI 규모의 생태계 성장 예산(그로스 그랜트)이 별도로 계속 발행되어 소각분을 일부 상쇄
- 토큰 효용: 거버넌스 투표, (신규) 프로토콜 수수료 소각을 통한 간접적 가치 축적, DAO 트레저리 관리 참여

## 4. 2026 로드맵 (핵심 관전 포인트)
1. **UNIfication 정착 여부 — 소각 vs 신규발행 순효과** ← 가장 중요
   - "헤드라인 소각량"과 "실질 순 디플레이션"의 괴리를 시장이 어떻게 재평가하는지가 핵심. 수개월치 온체인 데이터 축적 전까지는 "show me" 국면 지속 전망
2. **v4 Permissioned Pools / Hooks 생태계 확산**
   - 8/24 발표된 'Permissioned Pools'(v4 훅 표준)로 발행사 규정을 강제하는 허가형·토큰화 펀드 자산이 AMM 유동성에 직접 접근 가능해짐 — RWA 인프라로서의 확장. 감사(Audit) 리스크도 병존
3. **Unichain 성장**
   - 시퀀서 수익 → UNI 소각 파이프라인 규모 확대. 9/5 로빈후드 체인 통합 이후 사용자·거래량이 급증하며 소각 재원 확대 기대(섹션 5 참조)
4. **규제 환경**
   - 미국 내 DEX/DeFi 프로토콜에 대한 SEC 등 규제 기조 변화 — 2025년 조사 종결(reprieve) 이후에도 정책 리스크 상존

## 5. 시장 현황
- 가격 / 시총: 2026년 9월 초 기준 UNI $7.33(24h +18.32%), 최근 7일 저점~고점 $5.63~$7.33 범위에서 강한 상승 모멘텀.
- 최근 촉매: 9/5 로빈후드 체인 통합 이후 UNI 일일 활성사용자가 약 22,000명→220,000명으로 10배 급증, 거래량도 약 $1억→$10억 규모로 급증 — 로빈후드의 대규모 리테일 사용자층이 디파이로 유입된 결과로 분석(CMC AI). 기존 8/24 발표된 Permissioned Pools(v4 훅 표준)와 맞물려 수요가 확대되는 모습.

## 6. 실무 알림 사항
- 로빈후드 체인발 사용자·거래량 급증이 UNIfication 소각 파이프라인(로빈후드 체인 시퀀서 수익 포함)에 미치는 영향을 다음 분기 소각량 데이터로 확인할 것.
- 단기 +18% 급등 이후 되돌림 가능성이 있으므로 추격매수 시 변동성에 유의.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | 압도적 찬성률로 수수료 스위치·소각이 실제 가동되며 "거버넌스 전용 토큰 → 현금흐름 연동 자산"으로 서사 전환. DEX 거래량 1위 지위와 v4 Hooks(Permissioned Pools 포함)·Unichain을 통한 신규 수익원 확대 여지, 9월 로빈후드 체인 통합으로 사용자·거래량 급증 |
| **약세 논리** | 소각 발표 직후에도(2026년 2월) 매크로 알트코인 약세장 속에 UNI가 사이클 저점($2.90)을 기록 — "좋은 뉴스가 시장 상황을 이기지 못한" 전례. 연간 그로스 예산 발행이 순 디플레이션 효과를 희석. 타 DEX(PancakeSwap 등)와의 점유율 경쟁 및 DeFi 규제 불확실성 |
| **트리거** | ① 분기별 프로토콜 수수료·소각량 공개 데이터(연환산 추세 지속 여부) ② Unichain·로빈후드체인 TVL/거래량 성장 지속 여부 ③ P/Fee 배수의 시장 재평가(리레이팅) 여부 |

## 출처
- [Uniswap (UNI) — CoinGecko](https://www.coingecko.com/en/coins/uniswap)
- [Uniswap's UNIfication Upgrade Explained: How the $596M UNI Burn Reshapes Token Value in 2026 — KuCoin](https://www.kucoin.com/blog/en-uniswap-s-unification-upgrade-explained-how-the-596m-uni-burn-reshapes-token-value-in-2026)
- [Uniswap Governance Approves Fee Switch and 100M UNI Token Burn — CoinMarketCap Academy](https://coinmarketcap.com/academy/article/uniswap-governance-approves-fee-switch-and-100m-token-burn)
- [Uniswap DAO to activate 'fee switch,' burn almost $600m UNI — DL News](https://www.dlnews.com/articles/defi/uniswap-dao-to-activate-fee-switch-and-burn-100m-uni-tokens/)
- [Uniswap (UNI) Price Prediction 2026: The Fee Switch Is Live, 100 Million Tokens Are Burned — and the Price Hit a New Cycle Low Anyway — Bitget News](https://www.bitget.com/news/detail/12560605397905)
- [Uniswap's Reprieve Reveals the Uncertainty of DeFi Regulation — CLS Blue Sky Blog](https://clsbluesky.law.columbia.edu/2025/04/28/uniswaps-reprieve-reveals-the-uncertainty-of-defi-regulation/)
- [CoinMarketCap — Uniswap 최신 업데이트](https://coinmarketcap.com/cmc-ai/uniswap/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
