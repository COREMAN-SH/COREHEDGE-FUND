# SUI (Sui) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
**객체 중심(Object-Centric) 병렬처리 L1** — 계정 잔액이 아니라 "객체(Object)"를 상태 단위로 다뤄, 서로 무관한 트랜잭션을 동시에 처리함으로써 확장성과 초저지연을 동시에 노리는 Move 기반 블록체인.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **Move 언어** | Meta(구 Facebook) Diem에서 파생된 자원(resource) 지향 스마트컨트랙트 언어. 이중지불·재진입 버그를 타입 시스템 차원에서 방지 |
| **객체 모델(Object-Centric Model)** | 계정 기반이 아닌 객체 기반 상태 표현 → 서로 겹치지 않는 트랜잭션은 합의 없이 병렬 처리(Fast Path) 가능 |
| **Mysticeti 합의** | DAG 기반 BFT 합의 엔진. 리더 대기 없이 약 400ms대 파이널리티 달성, 기존 Narwhal-Bullshark 대비 지연 대폭 축소 |
| **스토리지 펀드(Storage Fund)** | 트랜잭션 저장 수수료를 영구 예치해 향후 검증인들의 데이터 저장 비용을 보전하는 자체 설계 메커니즘 |
| **zkLogin** | Google·Apple 등 Web2 계정으로 온체인 지갑을 생성하는 영지식 로그인 — 기관·일반 사용자 온보딩 마찰 축소 |
| **Walrus** | Sui 생태계의 탈중앙 대용량 스토리지(데이터 가용성) 프로토콜, AI 데이터셋·NFT 미디어 저장용으로 확장 중 |

## 3. SUI 토큰의 역할과 구조적 특징
- **최대 발행량 100억 SUI(고정)**, 유통량 약 40.75억 개(약 41%), 시가총액 약 29.6억 달러, FDV 약 72.7억 달러 (2026-09-01 CoinGecko 기준)
- 위임지분증명(DPoS) 구조 — 검증인이 SUI를 스테이킹하고, 지분 비율에 따라 결정론적으로(무작위성 없이) 보상 수령. 검증인은 자체적으로 수수료율(커미션)을 설정하며 ⚠️ 사전 고지 없이 변경 가능
- 가스비는 **계산 수수료 + 스토리지 수수료**로 분리. 스토리지 수수료는 스토리지 펀드에 적립되어 재스테이킹되고, 데이터 삭제 시 일부 환급도 가능
- Sui는 공식적으로 **"디플레이션이 버그가 아니라 설계된 기능"**이라고 명시 — 네트워크 사용량이 늘면 스토리지 펀드가 커지며 유통량 일부가 장기 잠김
- 토큰 효용: 스테이킹, 가스비 결제, dApp 내 유틸리티, 거버넌스 투표
- 언락 스케줄: 초기 투자자·팀 물량은 메인넷 후 1년 클리프를 거쳐 선형 언락 중. 2026-09-01 기준 월간 언락은 약 2,200만 SUI(유통량의 0.54% 수준)로 시장 충격은 제한적 — 다만 잠긴 물량(약 59%)이 여전히 대기 중

## 4. 2026 로드맵 (핵심 관전 포인트)
1. **기관 접근성 강화 (zkLogin + 컴플라이언스 서브넷)** ← 가장 중요
   - Web2 계정 기반 로그인과 "허가형 서브넷/컴플라이언스 객체"를 통해 은행·전통 금융기관이 규제 틀 안에서 퍼블릭 체인 처리량을 활용하도록 유도
2. **RWA(실물자산) 토큰화 확대**
   - 국채·부동산·원자재를 프로그래머블 객체로 표현해 기관 자금 유입 통로 마련
3. **Walrus 기반 AI/데이터 인프라**
   - 검증 가능한 온체인 머신러닝(zkML), AI 에이전트용 대용량 데이터 가용성 계층 구축
4. **현물 SUI ETF 확산** 🎯
   - 2026년 2월 21Shares(TSUI), Canary Capital·Grayscale(SUIS 등, 스테이킹 수익률 약 7% 포함) 현물 ETF가 잇따라 나스닥 상장 — 기관 자금 접근성의 구조적 이정표. 6월 이후 누적 순유입 지속 중(섹션 5 참조)

## 5. 시장 현황
- 가격 / 시총: 2026년 9월 초 기준 SUI $0.8055(24h +2.3%), 24시간 거래량 $599M 돌파하며 하강 채널에서 상승 전환 시도. 다만 직전 보도에서는 주간 -14% 하락도 함께 언급되는 등 변동성이 큰 구간(9/4~9/5 보도 혼재).
- 최근 촉매: 🚨 Phantom 지갑이 9/24부로 SUI 지원을 종료한다고 발표 — 약 20개월 만의 지원 철회이며, Sui TVL이 2025년 10월 고점 대비 -82% 급감한 것이 배경으로 지목됨(Coin Bureau, CoinGape, AMBCrypto, Altcoin Buzz 등 다수 매체, 8월 말~9월 초 보도 일치). Phantom 이용자는 데드라인 전 SUI를 타 지원 지갑으로 이전하거나 지원 자산으로 스왑해야 함. 상쇄 요인으로 9/4 Sui Foundation이 AI·디파이 개발자 대상 마일스톤 기반 $10M 생태계 펀드 출시를 발표.

## 6. 실무 알림 사항
- 🚨 Phantom 지갑 이용자는 9/24 SUI 지원 종료 전 자산을 Sui 공식 지갑(Sui Wallet) 등 타 지원 지갑으로 반드시 이전할 것 — 데드라인 임박 리스크.
- TVL이 전고점 대비 -82% 급감한 점은 Sui 생태계 유동성 위축의 강한 경고 신호 — 관련 디파이 포지션 보유 시 프로토콜별 TVL 추이를 재점검할 것. Switchboard 오라클 관련 이슈(지난주 알림)도 계속 유효.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | 스테이킹 수익까지 포함한 현물 ETF가 다수 상장되며 기관 자금 유입 채널 확보(12주 연속 순유입). Mysticeti 합의로 서브초 파이널리티 확보, 객체 모델 기반 병렬처리로 혼잡 시에도 가스비 예측 가능성 유지. RWA·zkLogin 조합으로 기관 온보딩 스토리 뚜렷 |
| **약세 논리** | 시총 대비 FDV 비율 0.41로 잠긴 물량(약 59%)이 여전히 크고, 매월 지속적 언락이 상방 압력으로 작용. Solana·Aptos(동일 Move 계열) 등과의 개발자·유동성 경쟁 심화. 검증인 커미션을 사전 고지 없이 바꿀 수 있는 구조는 스테이커에게 불리하게 작용할 잠재 리스크. Phantom 지갑 지원 종료(9/24)와 TVL -82% 급감은 생태계 위축을 보여주는 최신 경고 신호 |
| **트리거** | ① ETF 순유입 규모 추이(스테이킹형 ETF 특성상 유통 SUI 락업 효과 여부) ② 매월 언락 물량 소화 여부 ③ Phantom 지원 종료(9/24) 이후 SUI 매도 압력 현실화 여부 ④ Walrus/AI 내러티브의 실제 온체인 활성도(TVL, 트랜잭션 수) 반영 여부 |

## 출처
- [Sui Price: SUI/USD — CoinGecko](https://www.coingecko.com/en/coins/sui)
- [Tokenomics on Sui — Sui Documentation](https://docs.sui.io/develop/sui-architecture/tokenomics-overview)
- [Announcing Sui Tokenomics — Sui.io](https://www.sui.io/blog/sui-tokenomics)
- [SUI Token Unlock September 2026 — CoinGabbar](https://www.coingabbar.com/en/crypto-currency-news/sui-token-unlock-september-2026)
- [Sui Roadmap 2026: Building a Unified Value Network for AI Agents and Global Finance — KuCoin](https://www.kucoin.com/blog/sui-roadmap-2026-value-network)
- [Mysticeti: Revolutionizing Consensus on Sui — Decentralized Thoughts](https://decentralizedthoughts.github.io/2026-03-06-mysticeti-revolutionizing-consensus-on-sui/)
- [Canary Capital Launches First Spot SUI ETF with Staking — Sui.io](https://www.sui.io/blog/canary-capital-staking-spot-sui-etf-nasdaq-suis)
- [21Shares-Issued Spot SUI ETF (Nasdaq: TSUI) — Sui Blog](https://blog.sui.io/21shares-spot-sui-etf-nasdaq-tsui/)
- [Altcoin Buzz — Phantom Ends Sui Support on September 24 as SUI TVL Falls 82%](https://www.altcoinbuzz.io/phantom-ends-sui-support-september-24)
- [AMBCrypto — Phantom ends Sui Network support as TVL falls 82%](https://ambcrypto.com/phantom-ends-sui-network-support-as-tvl-falls-82-has-sui-become-a-dead-chain/)

---
*정보 제공 목적이며 투자 권유가 아님.*
