# LINK (Chainlink) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
스마트컨트랙트와 현실 세계(오프체인 데이터·시스템·타 체인)를 연결하는 "탈중앙 오라클 네트워크의 사실상 표준(industry standard)". DeFi를 넘어 은행·자본시장의 온체인 연동 인프라로 확장 중.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **Data Feeds / Data Streams** | 가격 등 실시간 데이터를 온체인에 공급하는 핵심 오라클 상품. DeFi TVL 대부분이 이에 의존 |
| **CCIP** (Cross-Chain Interoperability Protocol) | 서로 다른 블록체인 간 토큰·메시지 전송 표준. Chainlink의 차세대 핵심 사업 |
| **Proof of Reserve / CRE** | 실물자산·스테이블코인 담보 검증. Chainlink Runtime Environment(CRE)로 확장 중 |
| **Staking v0.2** | LINK 스테이킹으로 오라클 네트워크의 암호경제적 보안을 뒷받침 |
| **SWIFT / DTCC / Euroclear 연동** | 전통 금융 메시징망(SWIFT), 청산결제기관(DTCC)과의 온체인 브릿지 — TradFi 편입의 핵심 통로 |

## 3. 토크노믹스
- 최대/총 발행량 **10억 LINK**(고정, 추가 발행 없음), 유통량 약 **7.48억 LINK**(~75%)
- 스테이킹 v0.2: 기본 보상률 연 **4.5%**(커뮤니티 스테이커 실질 ~4.32%), 커뮤니티 최대 1.5만 LINK/노드 운영자 최대 7.5만 LINK, 전체 캡 4,500만 LINK
- **Chainlink Reserve**(2025.8 출범): 생태계·프로토콜 수익 일부로 LINK를 매입해 온체인 보유고에 적립 — "매수 지원" 메커니즘이나 소각(burn)은 아님
- ⚠️ 구조적 약점: 오라클 이용료가 LINK로 결제되지 않는 경우도 많아(스테이블코인/법정화폐 결제 옵션 존재), 네트워크 사용량 증가가 LINK 수요로 곧장 연결되는 가치 포착 경로가 아직 약함. 신규 체인 수수료를 보조하는 **SCALE 프로그램**도 장기적으로는 소진(sunset) 예정

## 4. 로드맵 · 관전 포인트
1. **CCIP 확장 및 기관 채택** ← 가장 중요
   - SWIFT의 글로벌 은행 네트워크(1만1천+ 금융기관)와 온체인 연동 파일럿 지속, DTCC·Euroclear 등 청산결제 인프라 협업 진행
2. **Chainlink Reserve 규모 확대** 🎯
   - 프로토콜 수익 기반 LINK 매입 누적분이 가치 포착 서사의 핵심 지표로 부상
3. **스테이킹 v0.2 확장 및 슬래싱 강화**
   - 장기적으로 사용자 수수료 기반 보상 체계로 전환하는 것이 목표
4. **LINK 현물 ETF 확산**
   - Bitwise CLNK ETF가 이미 NYSE Arca에 상장·거래 개시, Grayscale 등 후속 상품도 준비 중

## 5. 시장 현황
- 가격 / 시총: 2026-09-05 기준 LINK $11.65 부근에서 장기 보합권을 이탈, $12.64 이상 지속 종가 시 $15~$20 목표치가 제시됨. 직전 한 주 누적 상승률 약 +5%.
- 최근 촉매: 9/3 연 16조 달러 규모 결제처리사 Bottomline과 전략적 제휴 발표 — CCIP를 통해 600개 이상의 은행을 대상으로 국제송금 서비스를 제공하며, 기존 은행 시스템 표준을 유지한 채 안전한 크로스체인 결제를 구현. 9/5 공동창립자 세르게이 나자로프가 SWIFT 최대 연례행사 Sibos 2026(9/28~10/1, 마이애미)에서 토큰화·전통금융-온체인 연결을 주제로 기조연설을 진행할 예정이라고 발표.

## 6. 실무 알림 사항
- Bottomline 제휴는 CCIP의 신규 대형 기관 채택 사례 — 관련 은행망 연동의 실제 상용화 진행 상황을 계속 추적할 것.
- Sibos 2026(9/28~10/1) 기조연설을 전후로 관련 뉴스플로우·가격 변동성이 확대될 수 있음을 염두에 둘 것.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | 오라클 시장 사실상 독점적 지위, SWIFT/DTCC 등 TradFi 대형 기관과의 실질 파이프라인, CLNK 현물 ETF 상장으로 기관 접근성 개선, Chainlink Reserve로 가치 포착 서사 보강 |
| **약세 논리** | 네트워크 사용량 증가가 LINK 수요로 곧바로 이어지지 않는 가치 포착 구조적 한계, 유통 비중이 이미 높아 신규 희소성 서사가 약함, 경쟁 오라클(Pyth 등)의 시장 잠식 |
| **트리거** | Chainlink Reserve 누적 매입 규모, SWIFT/DTCC 파일럿의 실제 상용화 전환, CCIP TVS(Total Value Secured) 추이, 추가 현물 ETF 승인 |

## 출처
- [Chainlink (LINK) - CoinGecko](https://www.coingecko.com/en/coins/chainlink)
- [Chainlink Staking - Chainlink Economics](https://chain.link/economics/staking)
- [Introducing the Chainlink Reserve - Chainlink Blog](https://blog.chain.link/chainlink-reserve-strategic-link-reserve/)
- [The Swift and Chainlink Partnership - Chainlink](https://chain.link/blog/the-swift-and-chainlink-partnership)
- [Bitwise Chainlink ETF Approved for NYSE Arca Listing Under CLNK Ticker - TradingView](https://www.tradingview.com/news/coinpedia:ce4bcffd8094b:0-bitwise-chainlink-etf-approved-for-nyse-arca-listing-under-clnk-ticker/)
- [Chainlink CCIP: How 11,000 Banks Got a Direct Line to Blockchain - BlockEden.xyz](https://blockeden.xyz/blog/2026/01/11/chainlink-ccip-cross-chain-tradfi-bridge-infrastructure/)
- [CoinMarketCap — Chainlink 최신 업데이트](https://coinmarketcap.com/cmc-ai/chainlink/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
