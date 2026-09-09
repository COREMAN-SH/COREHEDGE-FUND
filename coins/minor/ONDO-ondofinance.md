# ONDO (Ondo Finance) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
**실물자산 토큰화(RWA) 대표주** — 미국 단기국채 등을 온체인 토큰(OUSG, USDY)으로 발행해온 프로토콜이었으나, 2026년 8월 자체 L1(Ondo Chain) 계획을 폐기하고 **TEE(신뢰실행환경) 기반 비공개 매칭엔진 + 이더리움 정산**의 "Ondo Network" 구조로 전략을 전면 수정.

## 2. 핵심 기술 스택 (2026년 8월 전략 전환 반영)
| 구성요소 | 역할 | 비고 |
|---|---|---|
| ~~Ondo Chain (자체 L1)~~ | RWA 특화 검증인 세트를 갖춘 독자 블록체인으로 2024년부터 17개월 개발 | **2026-07-28 공식 폐기** — 자체 합의·복제·투명성 계층이 오히려 지연과 주문흐름(order flow) 노출을 유발한다고 판단 |
| **Ondo Network (TEE 기반)** | 주문 매칭·체결을 하드웨어 격리 보안 엔클레이브(TEE) 내부에서 실행 | 각 엔클레이브는 하드웨어 지문을 생성, 독립 검증자(attester)가 승인된 코드와 대조해 검증. 키 조각을 분산 보관해 Ondo 단독으로도 완전한 키를 보유하지 않는 구조. 첫 애플리케이션으로 무기한선물 거래소 'Ondo Perps' 출시 |
| **이더리움 정산 계층** | 최종 자산 이전·결제는 기존 이더리움 메인넷에서 처리 | 전통 금융거래소(비공개 매칭엔진 + 공개 청산소) 구조를 모사 |
| **OUSG / USDY** | 각각 기관용 토큰화 국채펀드, 개인·기관용 수익형 스테이블코인(국채 담보) | Ondo의 기존 핵심 RWA 상품, TEE 전환과 별개로 지속 운영. 최근 솔라나 체인에서의 성장이 두드러짐(섹션 5 참조) |
| **Oasis Pro 인수** | FINRA 라이선스 보유 규제형 ATS(대체거래시스템) 확보 | 미국 내 토큰화 증권·펀드를 규제 준수 하에 유통하기 위한 브로커-딜러/거래소 인프라 |

- 전략 전환 배경: 호주증권거래소(ASX)의 블록체인 교체 실패 사례(약 2억5,500만 호주달러 손실)를 반면교사로 인용하며, "단일 운영자의 주문장(order book)에는 별도 체인이 신뢰를 더하지 못하고 복잡성만 가중한다"는 논리
- 성과 지표: TEE 기반 신규 구조로 3주 만에 약 60억 달러 규모의 명목 계약 처리 발표. 8/29 기준 토큰화 주식 산업 전체 월간 이전액이 전월 대비 +415% 급증해 $295억 기록, Ondo가 $8.428억(점유율 33%)로 Kraken·Binance를 제치고 1위(CMC AI)

## 3. ONDO 토큰의 역할과 구조적 약점
- **최대 발행량 100억 ONDO(고정)**, 유통량 약 48.7억 개(약 49~53%), 시총 약 16.9억 달러, FDV 약 34.6억 달러 (2026-09-01 CoinGecko 기준)
- 배분 구조: 생태계 성장 52.1% / 프로토콜 개발 33.0% / 프라이빗 세일 12.9% / 커뮤니티 액세스 세일 2.0%
- ⚠️ **대규모 언락 대기**: 약 46.7%(약 46.7억 개)가 여전히 잠겨 있으며, 선형 베스팅이 2029년 1월까지 지속. 단기간 내 수억 달러 규모(프라이빗 세일·프로토콜 개발·생태계 물량 합산 약 19억 개, 시총의 약 19%) 언락 구간이 예정되어 있어 지속적 매도 압력 우려
- ⚠️ **가치 포착(Value Capture) 문제**: ONDO 토큰 자체는 프로토콜 거버넌스·인센티브 배분이 핵심 역할이며, OUSG·USDY 등 실제 수익창출 상품의 수수료가 ONDO 보유자에게 직접 귀속되는 구조는 제한적 — RWA 점유율 1위(월간 이전액 기준)라는 사업 성과가 반드시 토큰 가격에 비례하지 않을 수 있음
- 🚨 **거버넌스 리스크(2026-05~)**: 창업자 Nathan Allman이 2026년 5월 사망한 이후 이사회 공백 상태에서, 사장이었던 Ian De Bode가 이사회 승인 없이 CEO를 자임했다는 논란 발생. 창업자의 모친 Kathleen Allman이 유산관리인 자격으로 7/24 이사회 표결을 통해 De Bode 해임·본인 임시 CEO 선임을 시도하고 델라웨어 형평법원에 소송 제기(사건번호 2026-0978)해 "중대 법인행위" 잠정 금지를 요청 — 9월 초 현재도 새로운 법원 판단 없이 미해결 상태(상세 뉴스는 섹션 5·6 참조)

## 4. 2026 로드맵 (핵심 관전 포인트)
1. **Ondo Network(TEE) 안정적 가동 여부** ← 가장 중요
   - 자체 체인 포기 이후 TEE 기반 구조가 기관 신뢰(규제 대응, 보안 사고 이력)를 얻을 수 있는지가 관건. 'Ondo Perps'를 시작으로 후속 애플리케이션 확대 여부
2. **Oasis Pro 기반 규제형 토큰화 증권 확대**
   - FINRA 라이선스를 활용해 미국 내 토큰화 주식·펀드 유통을 얼마나 빠르게 스케일업하는지 — 이미 토큰화 주식 월간 이전액 점유율 33%로 1위
3. **경영권 분쟁 해소** 🚨
   - 델라웨어 법원(사건번호 2026-0978) 판결/합의 시점과 결과 — 리더십 공백 장기화 시 파트너십·상품 로드맵 지연 리스크
4. **대형 인수 검토**
   - RWA 시장(약 360억 달러 규모로 성장) 내 5억 달러 규모 인수설 등 M&A를 통한 몸집 키우기 시도

## 5. 시장 현황
- 가격 / 시총: 2026년 9월 초 기준 ONDO $0.3743(24h +1.5%). 9/5 기준 $0.31 회복이 필요한 기술적 약세 구간으로 평가되며, 5월 이후 이어진 장기 하락추세선을 여전히 하회.
- 최근 촉매: 솔라나 생태계 RWA가 최근 30일간 $348M 순유입을 기록하며 총 규모 $423M(역대 최고)로 성장 — ONDO의 USDY·OUSG 상품이 솔라나에서 강한 성과를 내며 크게 기여(9/5, CMC AI). 경영권 분쟁(델라웨어 형평법원 소송, 사건번호 2026-0978)은 이번 주 새로운 법원 판단 없이 미해결 상태로 지속. 금리 정책 변화에 민감한 알트코인으로 시장 관찰 대상에 재차 포함(9/4).

## 6. 실무 알림 사항
- 솔라나 체인 상의 USDY·OUSG 성장이 이어지는지 온체인 데이터로 계속 확인 — 신규 유동성 유입처로서 유효.
- 델라웨어 소송(사건번호 2026-0978)은 여전히 미해결 — 법원 심리 일정 발표 시 즉시 반영 필요. 'Ondo Network' 전환 이후 자산 브릿지/커스터디 구조가 TEE 기반으로 바뀌므로, USDY 등 보유 상품의 컨트랙트 주소 변경 여부를 거래 전 재확인(지난주 알림 유효 지속).

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | RWA(국채·토큰화 주식) 섹터 선두 지위(토큰화 주식 월간 이전액 점유율 33%로 1위), Oasis Pro 인수로 규제 준수형 토큰화 증권 인프라 선점, TEE 전환으로 개발 리소스를 매칭엔진 성능에 집중해 실사용 지표(3주 60억 달러 명목거래, Ondo Perps 출시) 확보, 솔라나 체인 RWA 성장에서 USDY·OUSG의 기여도 확대 |
| **약세 논리** | 창업자 사망 이후 경영권 분쟁이 델라웨어 법원에서 미해결 상태로 남아있어 지배구조 리스크가 이례적으로 큼(상세는 섹션 5·6 참조). 자체 체인 포기가 "실용적 피벗"인 동시에 "17개월 개발 실패"로도 해석 가능. 46%대의 대규모 잠긴 물량과 2029년까지 이어지는 선형 언락이 구조적 매도 압력으로 작용 |
| **트리거** | ① 델라웨어 법원의 경영권 분쟁 심리 일정 및 결과 ② Ondo Network(TEE) 보안사고 유무 및 기관 채택 속도 ③ 분기별 ONDO 언락 물량과 시장 소화 여부 |

## 출처
- [Ondo (ONDO) — CoinGecko](https://www.coingecko.com/en/coins/ondo-finance)
- [RWA tokenization news: Ondo drops blockchain plans for private, high-speed trading network — CoinDesk](https://www.coindesk.com/business/2026/07/28/ondo-drops-tokenized-asset-blockchain-plans-for-private-high-speed-trading-network)
- [Ondo Finance Abandons Ondo Chain After 17 Months, Keeps ONDO Settlement on Ethereum — COINOTAG](https://en.coinotag.com/ondo-finance-abandons-ondo-chain-keeps-ethereum-settlement)
- [Power struggle erupts at Ondo Finance after founder's death — CoinDesk](https://www.coindesk.com/policy/2026/08/06/power-struggle-erupts-at-ondo-finance-after-founder-s-death)
- [Late Ondo founder's mother seeks control of company and removal of De Bode as CEO — The Block](https://www.theblock.co/news/regulation/2026-08-06-late-ondo-founders-mother-seeks-control-of-company-and-removal-of-de-bode-as-ceo-411006)
- [Ondo (ONDO) Token Unlocks and Vesting: Schedule and Tokenomics — DropsTab](https://dropstab.com/coins/ondo-finance/vesting)
- [Ondo Finance's Oasis Pro Markets Secures FINRA Authorizations — Yahoo Finance](https://finance.yahoo.com/markets/crypto/articles/ondo-finances-oasis-pro-markets-133000099.html)
- [Ondo Finance weighs $500M deal as RWA market hits $36B — crypto.news](https://crypto.news/ondo-finance-weighs-500-million-acquisition-tokenized-securities/)
- [CoinMarketCap — Ondo 최신 업데이트](https://coinmarketcap.com/cmc-ai/ondo-finance/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
