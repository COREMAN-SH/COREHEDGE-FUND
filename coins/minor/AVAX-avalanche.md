# AVAX (Avalanche) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
서브넷(현재 명칭 "Avalanche L1") 아키텍처를 통해 누구나 자체 규칙을 가진 독립 블록체인을 손쉽게 띄울 수 있는 모듈형 레이어1 플랫폼. 기관·기업용 프라이빗/퍼미션드 체인 인프라로 포지셔닝 강화 중.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **Avalanche Consensus** | 밀리초 단위 파이널리티를 제공하는 독자적 합의 프로토콜(스노우맨 계열) |
| **Primary Network (P/X/C-Chain)** | 플랫폼체인(검증자 관리)·거래체인·컨트랙트체인(EVM 호환)으로 역할 분리 |
| **Avalanche L1** (구 서브넷) | 커스텀 가스토큰·검증자셋·퍼미션 정책을 가진 독립 체인을 낮은 비용으로 생성 |
| **ICM / ICTT** (Interchain Messaging / Token Transfer) | L1 간 메시지·자산 전송 표준. 코스모스 IBC와 유사한 역할 |
| **Avalanche9000 업그레이드** | 서브넷 운영 최소 자본 요구를 대폭 인하하고(수십만 달러 → 수백 달러 수준) L1 검증자 관리를 스마트컨트랙트화(ACP-77), C-Chain 최소 기본수수료도 25nAVAX → 1nAVAX로 인하(ACP-125) |

## 3. 토크노믹스
- 최대 발행량 **7.2억 AVAX**(고정 상한), 유통량 약 **4.32억 AVAX**(~60%)
- 검증자 최소 스테이킹 2,000 AVAX, 위임자 최소 25 AVAX, 스테이킹 기간 2주~1년, 현재 스테이킹 수익률 약 **6.65% APY**(변동)
- 모든 트랜잭션 수수료는 **소각(burn)**되어 영구적으로 유통량에서 제거 — 사용량 증가 시 디플레이션 압력으로 작용
- ⚠️ 구조적 약점: Avalanche9000으로 L1 생성 장벽이 크게 낮아지면서, L1들이 자체 가스토큰을 쓰는 경우 해당 체인의 활동이 AVAX 수요로 직결되지 않는 "가치 포착 희석" 문제가 부각 — L1이 늘어날수록 생태계는 커지지만 AVAX 토큰 자체의 몫은 상대적으로 작아질 수 있음

## 4. 로드맵 · 관전 포인트
1. **기관·엔터프라이즈용 L1 확산** ← 가장 중요
   - KKR(Securitize 경유 사모펀드 토큰화), Homium(주택지분 대출), Balcony(뉴저지주 2,400억 달러 규모 부동산 등기 디지털화), WisdomTree Connect(13개 토큰화 펀드) 등 실물자산(RWA) 온체인화 파일럿 확대
2. **VanEck AVAX 현물 ETF(VAVX) 출시** 🎯
   - 2026년 1월 미국 최초의 AVAX 현물 ETF로 출시(스테이킹 수익 포함 구조), 이후 Bitwise·Grayscale 등도 AVAX 현물 보유 상품 확대. 8/27~28 찰스 슈왑도 AVAX 거래 지원 추가(섹션 5 참조)
3. **Avalanche9000 이후 L1 생태계 지속 확장**
   - 검증자 운영비용 절감 효과가 실제 신규 L1 런칭 건수 증가로 이어지는지가 관전 포인트
4. **ICM 기반 크로스 L1 유동성 통합**
   - 파편화된 L1들 간 자산·메시지 이동을 매끄럽게 만드는 인터체인 메시징 고도화

## 5. 시장 현황
- 가격 / 시총: 2026년 9월 초 기준 AVAX $7.64(24h +0.77%), $6.50~7.00 지지·$6.90~7.09 저항 구간에서 등락 — 일부 트레이더는 최근 매수 신호로 +19.5% 수익을 보고.
- 최근 촉매: 9/5 한국 금융당국이 주식·채권·펀드를 토큰화 인프라로 이전하는 3단계 로드맵(1단계 2027-02-04 개시 예정)을 발표했고, 일부 매체는 아발란체가 해당 인프라 후보로 거론되고 있다고 보도(국내 주요 매체의 아발란체 특정 언급은 추가 교차검증 필요). 참고로 8/27~28 찰스 슈왑의 AVAX·SOL·LINK 거래 지원 추가 발표는 지난 갱신에서 이미 반영된 내용으로, 이번 주 신규 촉매는 아님.

## 6. 실무 알림 사항
- 한국 STO(토큰증권) 3단계 로드맵과 아발란체의 구체적 연관성은 국내 1차 자료로 아직 명확히 확인되지 않음 — 공식 발표나 국내 주요 매체 확인 시 즉시 업데이트할 것.
- RWA TVL $3B대(8/29 기준) 유지 여부와 신규 기관 파트너십 발표 여부를 계속 추적.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | JPMorgan Kinexys, KKR, Deloitte 등 굵직한 기관·기업 파트너십 다수 확보, VAVX·슈왑 등 현물 ETF·브로커리지로 기관 자금 접근성 개선, 수수료 소각 구조로 사용량 증가 시 디플레이션 유인 |
| **약세 논리** | L1이 자체 가스토큰을 사용할 경우 생태계 성장이 AVAX 수요로 직결되지 않는 가치 포착 희석 리스크, 경쟁 모듈형 L1/L2(코스모스, 폴카닷, 옵티미즘 스택 등)와의 치열한 경쟁, 유통량이 최대 발행량의 60% 수준으로 향후 추가 언락 부담 존재 |
| **트리거** | 신규 기관형 L1 런칭·RWA 온체인화 파일럿의 실사용 전환, VAVX 등 ETF·브로커리지 자금 유입 추이, C-Chain/L1 수수료 소각량(디플레이션 압력) 추이 |

## 출처
- [Avalanche (AVAX) - CoinGecko](https://www.coingecko.com/en/coins/avalanche)
- [Avalanche Review 2026: AVAX, Avalanche9000, L1s and Risks - Coin Bureau](https://coinbureau.com/review/avalanche-avax)
- [Tokens - Avax.Network](https://www.avax.network/about/tokens)
- [Avalanche (AVAX) Staking — Live APY - Staking Rewards](https://www.stakingrewards.com/asset/avalanche)
- [VanEck Introduces Another First with Launch of the VanEck Avalanche ETF (VAVX) - VanEck](https://www.vaneck.com/us/en/our-firm/media-coverage/vaneck-introduces-another-first-with-launch-of-the-vaneck-avalanche-etf-vavx/)
- [Avalanche Q1 2026 Report - Nansen](https://nansen.ai/post/avalanche-q1-2026-report)
- [CoinMarketCap — Avalanche 최신 업데이트](https://coinmarketcap.com/cmc-ai/avalanche/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
