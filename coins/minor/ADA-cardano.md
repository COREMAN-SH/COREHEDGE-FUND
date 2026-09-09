# ADA (Cardano) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
피어리뷰(동료평가) 학술 연구를 거쳐 설계된 지분증명(PoS) 스마트컨트랙트 플랫폼. "먼저 연구, 그다음 코드(research-first)" 개발 철학과 신중한 온체인 거버넌스가 특징.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **Ouroboros** | 세계 최초로 피어리뷰 학술 논문을 거쳐 검증된 PoS 합의 프로토콜 |
| **eUTxO 모델** | 비트코인 UTXO를 확장한 트랜잭션 모델. 예측 가능한 수수료·병렬 처리에 유리하나 EVM 대비 개발 생태계는 협소 |
| **Hydra** | 상태채널 기반 레이어2 확장 솔루션, 초당 처리량 대폭 향상 목표 |
| **Ouroboros Leios** | 처리량 자체를 늘리는 차세대 합의 계층 업그레이드(파이프라이닝 방식) |
| **Midnight** | ZK 기반 프라이버시 사이드체인. 2025.11 NIGHT 토큰 에어드랍 완료, 2026년 확장 예정 |
| **Voltaire (온체인 거버넌스)** | ADA 보유자가 직접 프로토콜 변경·트레저리 지출을 투표로 결정하는 거버넌스 체계 |

## 3. 토크노믹스
- 최대 발행량 **450억 ADA**, 유통량 약 **375억 ADA**(~83%)
- 매 에폭(epoch)마다 리저브(reserve)의 0.3%가 스테이킹 보상+트레저리로 분배되는 통화팽창 방식 → 연간 인플레이션 약 2% 내외, 초기 리저브 139억 ADA에서 비선형적으로 점진 감소(시간이 지날수록 수수료 비중 확대 설계)
- 현재 스테이킹 보상률 약 **5~6% APY**(위임형 PoS, 락업 없이 유동성 유지 가능)
- 수익 배분: 통화팽창+수수료 수입의 20%는 트레저리로, 80%는 스테이크풀 운영자·위임자에게 분배
- ⚠️ 구조적 약점: 온체인 활동(DeFi TVL, 트랜잭션 수)이 시총 대비 낮은 편으로 "연구는 훌륭하나 실사용이 더디다"는 비판이 지속 — Midnight·RealFi 등 신규 유스케이스가 이 간극을 메울 수 있을지가 관건

## 4. 로드맵 · 관전 포인트
1. **Midnight 사이드체인 본격 확장** ← 가장 중요
   - 2025.11 NIGHT 토큰 에어드랍 완료, 2026년 프라이버시 지원 스마트컨트랙트·RealFi(규제 준수형 DeFi) 유스케이스 확대가 관건
2. **Ouroboros Leios 도입**
   - 처리량 병목 해소를 위한 차세대 합의 레이어. 실제 메인넷 배포 시점이 핵심 관전 포인트
3. **Hydra L2 상용화 확대**
   - 상태채널 기반 확장으로 초당 트랜잭션 처리량 대폭 개선 목표
4. **ADA 현물 ETF** 🎯
   - Grayscale이 2026년 10월 이전 ADA 현물 ETF 출시를 목표로 SEC 절차 진행 중(75일 패스트트랙 사례 존재) — 승인 시 기관 자금 유입 트리거
5. **Hoskinson의 트레저리 재편 전략**
   - 대규모 트레저리 자금을 RealFi·파트너십 등 생태계 성장에 전략적으로 투입하는 새 로드맵 발표

## 5. 시장 현황
- 가격 / 시총: 2026-09-05 4.4% 하락하며 $0.224→$0.209 부근까지 조정, 이후 반등해 $0.2209(24h +4.93%) 거래. 8/27 주간 +20%대 랠리 이후 되돌림 국면.
- 최근 촉매: 9/5 기준 주간 활성주소가 -37.4% 급감해 사용자 참여도 약화 신호가 나온 반면, DEX 거래량은 오히려 3배 증가한 $7.28M을 기록하는 등 온체인 신호가 엇갈림. 최근 2주간 TVL은 약 3,134만 ADA 증가했고, $1.28M 규모의 (주로 롱포지션) 레버리지 청산도 발생. 규제 준수형 디파이 'RealFi' 메인넷이 10/1 출시를 앞두고 있어 다음 주 이후 실사용 지표 확인이 가능할 전망.

## 6. 실무 알림 사항
- 활성주소 급감과 TVL·DEX 거래량 증가가 동시에 나타나는 혼조 신호 — 추격매수보다 RealFi 10/1 메인넷 출시 등 실질 촉매를 확인한 뒤 대응할 것을 권장.
- $0.22 위 안착 여부가 단기 방향성의 핵심 — 하방 지지선 $0.1709 이탈 여부도 함께 체크.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | 학술 피어리뷰 기반의 검증된 개발 프로세스로 보안·안정성 리스크가 낮음, Midnight/Leios/Hydra 등 다년간 준비한 굵직한 업그레이드가 2026년 동시다발적으로 실현 단계, ETF 승인 절차가 상대적으로 빠르게 진행 중 |
| **약세 논리** | "연구 우선" 철학이 실사용·개발자 유입 속도를 늦춘다는 비판이 오래 지속, EVM 생태계 대비 dApp·TVL 규모가 작음, 최근 랠리도 활성주소 급감 등 혼조 온체인 신호 속에서 진행 |
| **트리거** | Midnight RealFi 유스케이스의 실사용 지표(10/1 메인넷 출시), Leios 메인넷 배포 일정 준수 여부, ADA 현물 ETF 승인/출시, 온체인 TVL·활성 주소 추이 |

## 출처
- [Cardano (ADA) - CoinGecko](https://www.coingecko.com/en/coins/cardano)
- [Cardano: ADA Tokenomics - Figment.io](https://www.figment.io/insights/cardano-ada-tokenomics/)
- [Cardano Review 2026: Midnight, Hydra and Other Updates - Coin Bureau](https://coinbureau.com/review/cardano-review)
- [Grayscale Investments Eyes Cardano (ADA) ETF Debut In Late 2026 - Crowdfund Insider](https://www.crowdfundinsider.com/2026/05/278376-grayscale-investments-eyes-cardano-ada-etf-debut-in-late-2026/)
- [Grayscale Plans Cardano ETF Launch by October 2026 - Phemex News](https://phemex.com/news/article/grayscale-eyes-october-2026-launch-for-cardano-etf-80108)
- [Cardano Gains Momentum with Midnight Airdrop and Grayscale ETF Developments - Cryptolifedigital](https://cryptolifedigital.com/2025/11/12/cardano-gains-momentum-with-midnight-airdrop-and-grayscale-etf-developments/)
- [Cardano (ADA) 2026: A Deep Dive into Leios, Midnight and Voltaire - WEEX](https://www.weex.com/wiki/article/cardano-ada-2026-has-the-academic-vision-finally-delivered-a-deep-dive-into-leios-midnight-and-the-billion-dollar-governance-era-48579)
- [CoinMarketCap — Cardano 최신 업데이트](https://coinmarketcap.com/cmc-ai/cardano/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
