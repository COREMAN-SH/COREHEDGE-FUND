# 미국 주식 섹터 분류 체계 가이드 — GICS · ICB · 나스닥100

작성: 2026-09-01 · 관련: `stocks/00-INDEX.md`, `framework/financial-statements-guide.md`

이 문서가 답하는 질문: **"섹터"라는 게 누가 정한 무엇이고, 왜 같은 회사가 자료마다 다른 섹터로 나오는가.**

---

## 0. 3줄 요약

1. 섹터 분류는 자연법칙이 아니라 **두 회사(MSCI+S&P의 GICS, FTSE Russell의 ICB)가 파는 상품**이다.
2. 둘은 최상위 카테고리가 11개로 같지만 **구성이 다르다.** GICS엔 Communication Services가 있고 ICB엔 없다. 결제기업은 GICS에선 금융, ICB에선 산업재다.
3. **나스닥100은 ICB를 쓴다.** 그래서 "비금융 기업만"이라는 규칙에도 PayPal이 들어 있다. GICS 기준 섹터 ETF(XLK 등)와 나스닥100의 섹터 비중을 섞어 보면 반드시 틀린다.

---

## 1. GICS (Global Industry Classification Standard)

**제정**: MSCI + S&P Dow Jones Indices 공동, 1999년. 현재 구조는 2023-03-17 개편본.

### 4계층

| 계층 | 코드 자릿수 | 개수 |
|---|---|---|
| Sector (섹터) | 2자리 | **11** |
| Industry Group (산업군) | 4자리 | **25** |
| Industry (산업) | 6자리 | **74** |
| Sub-Industry (하위산업) | 8자리 | **163** |

### 11개 섹터

| 영문 | 한글 | 실제로 담기는 것 |
|---|---|---|
| Energy | 에너지 | 석유·가스 탐사/시추/정제, 에너지 장비·서비스 |
| Materials | 소재 | 화학, 금속·광업, 종이·포장, 산업가스 |
| Industrials | 산업재 | 항공우주·방산, 기계, 운송(철도·트럭·항공), 건설, 상업서비스 |
| Consumer Discretionary | 임의소비재 | 자동차, 내구재, 호텔·레저·외식, 의류, Broadline Retail |
| Consumer Staples | 필수소비재 | 식음료, 담배, 가정·개인용품, 필수소비재 유통(마트) |
| Health Care | 헬스케어 | 제약, 바이오텍, 의료기기, 헬스케어 서비스 |
| Financials | 금융 | 은행, 보험, 자산운용, **결제·거래처리(2023 신설)**, 소비자금융 |
| Information Technology | 정보기술 | 반도체, 하드웨어, 소프트웨어, IT서비스 |
| Communication Services | 커뮤니케이션서비스 | 통신사, 미디어·엔터, 인터랙티브미디어(구글·메타), 게임 |
| Utilities | 유틸리티 | 전력·가스·수도, 독립발전 |
| Real Estate | 부동산 | REITs, 부동산 관리·개발 |

### 배정 원칙 — 여기가 핵심

- 회사는 4계층 전부에서 **딱 하나의 그룹**에만 속한다. 겸업이 아무리 커도 복수 배정 없다.
- **1차 기준은 매출.** 매출의 과반(통상 60%+)을 만드는 사업활동으로 배정.
- 60%를 넘는 사업이 없으면 **매출과 이익 양쪽에서 과반**을 차지하는 쪽으로.
- 시장의 인식(market perception)은 부차적 참고요소.

> **"주된 사업활동 기준이지 매출 기준이 아니다"는 흔한 오해다.** 실제로는 *매출로 판별한 주된 사업활동*이다. 이 한 줄이 아마존·테슬라 분류 논란을 대부분 설명한다.

### 개편 이력

**2018-09** — Telecommunication Services 폐지 → **Communication Services** 신설. 구글·메타·넷플릭스가 IT·임의소비재에서 이쪽으로 이동.

**2023-03-17** — 역대 최대 개편

| 대상 | 이전 | 이후 |
|---|---|---|
| Visa, Mastercard, **PayPal**, Fiserv, FIS, Global Payments | IT (Data Processing) | **Financials** (신설 `Transaction & Payment Processing Services`) |
| Target, Dollar General, Dollar Tree | Consumer Discretionary | **Consumer Staples** ("월마트와 유사한 생필품 비중") |
| 아마존 등 종합 온라인소매 | Internet & Direct Marketing Retail | **Broadline Retail** (신설) |
| 급여처리(ADP·PAYX) | IT | **Industrials** |

결과: S&P 500 내 IT 비중 27.7% → 24.5%, 금융 11.5% → 14.2%.

---

## 2. ICB (Industry Classification Benchmark)

**제정**: FTSE Russell (LSEG 자회사). 2005년 FTSE·다우존스 공동 출범 → 2011년 이후 FTSE 단독.

### 4계층

| 계층 | 개수 |
|---|---|
| Industry (산업) | **11** |
| Supersector (슈퍼섹터) | **20** |
| Sector (섹터) | **45** |
| Subsector (서브섹터) | **173** |

### 11개 Industry

Technology(기술) · Telecommunications(통신) · Health Care(헬스케어) · Financials(금융) · Real Estate(부동산) · Consumer Discretionary(임의소비재) · Consumer Staples(필수소비재) · Industrials(산업재) · Basic Materials(기초소재) · Energy(에너지) · Utilities(유틸리티)

### GICS와의 결정적 차이 4가지

| 항목 | GICS | ICB |
|---|---|---|
| **Communication Services** | 독립 섹터로 존재 (통신+미디어+인터랙티브) | **없음.** 통신은 독립 유지, 미디어는 Consumer Discretionary 하위 |
| **결제기업** | **Financials** (2023~) | **Industrials 또는 Technology.** 금융 아님 |
| **최상위 명칭** | Information Technology / Materials | Technology / Basic Materials — Technology와 Telecommunications를 분리 |
| **주 사용처** | S&P·MSCI 지수, 미국 섹터 ETF(XLK·XLF·XLY…), 미국 셀사이드 리서치 | FTSE·STOXX, **나스닥 지수 시리즈 전체(나스닥100 포함)**, 유럽계 리서치 |

---

## 3. 왜 갈리는가 — 실제 사례

| 종목 | 분류 | 왜 |
|---|---|---|
| **AMZN** | Consumer Discretionary / Broadline Retail | 온라인스토어 43% + 오프라인 4% + 3P 판매서비스 23% = **소매 매출 70%**. 60% 기준을 넘어 소매로 확정. AWS는 매출 21%뿐이라 IT로 옮길 근거가 안 된다 — **영업이익의 60%를 내도 소용없다. 분류는 매출을 본다** |
| **TSLA** | Consumer Discretionary / Automobile Manufacturers | 매출 73%가 자동차 판매. 로보택시·휴머노이드·에너지는 아직 매출 기준 미달 |
| **COST / WMT** | Consumer Staples | 식품·생필품 매출이 과반. 취급 상품의 생필품 비중이 Staples/Discretionary를 가른다 |
| **PYPL** | **GICS: Financials / ICB: Industrials** | 2023 GICS 개편으로 금융이 됐다. 그런데 나스닥100은 ICB로 판정하고 ICB에서 PayPal은 Industrials다 → **"비금융만" 규칙에도 편입 유지.** 나스닥 공식 자료도 PYPL을 Industrials로 표기 |
| **NFLX** | GICS: Communication Services / ICB: Consumer Discretionary 계열 미디어 | ICB에는 Communication Services라는 최상위 산업 자체가 없다 |
| **MSTR** | Software (GICS·ICB 모두) | 주가는 사실상 BTC 프록시지만, 분류체계는 **"무엇을 팔아 매출이 나는가"**를 볼 뿐 **"주가가 무엇에 연동되는가"**는 보지 않는다. 다만 ICB가 향후 디지털자산 트레저리 기업을 금융으로 재분류하면 나스닥100 편출 가능성 존재 |
| **ADP / PAYX** | Industrials / Human Resource & Employment Services | 급여자금을 다루지만 수신·대출 라이선스가 없다. GICS·ICB 모두 금융 아님 |

### 분류가 실제로 논쟁 중인 종목 (데이터 제공사별로 다르게 표기됨)

- **ROP (Roper Technologies)** — 매출 대부분이 수직시장 소프트웨어인데 Industrials로 표기되는 자료와 Information Technology로 표기되는 자료가 공존. **이 종목이 PER 18배로 저평가로 보이는 이유의 절반이 "산업재 취급"이다**
- **APP (AppLovin)** — 광고 플랫폼. Communication Services(인터랙티브미디어)와 Information Technology(소프트웨어) 양쪽 표기가 존재
- **CRWV / NBIS** — GPU 임대업. IT Services인지 Communication Services인지 제공사별 상이
- **SNDK / WDC / STX** — 흔히 "반도체"로 묶이지만 GICS 정식 분류는 **Technology Hardware, Storage & Peripherals**. 반도체 섹터 지표(SOX 등)와 비교할 때 주의

> **실무 원칙**: 분류가 논쟁적인 종목은 어느 라벨이 맞는지 다투지 말고, **어느 벤치마크·ETF를 쓰는지에 따라 라벨을 고정**하고 그 안에서 일관되게 분석한다.

---

## 4. 나스닥100 지수 방법론 (2026년 개정 반영)

### 4.1 편입 자격

1. **상장**: 나스닥 Global Select / Global Market 단독 상장 (Capital Market 제외)
2. **비금융**: **ICB 기준** Financials 산업이 아닐 것. REIT 아닌 부동산 회사는 편입 가능
3. **유동성**: 3개월 평균 일일거래대금 $5M 이상

> TSM이 시총 상위인데도 나스닥100에 없는 이유는 시총이 아니라 **NYSE 상장**이기 때문이다.

### 4.2 2026-05-01 개정 — 구조적 개편

| 이전 | 이후 |
|---|---|
| 연 1회 12월 리컨스티튜션 | **분기 리뷰(3·6·9·12월)** 신설 |
| 신규상장 편입 규정 없음 | **Fast Entry** — 상장 7거래일째 시총 순위 top 40이면 조기 심사, 통상 15거래일 전후 편입 |
| 최소 유동비율 10% 요건 | 폐지 → **유동비율 33⅓% 기준의 단계적 가중**. 나스닥 공식 표현은 "3배 캡"이 아니라 33⅓% 임계값이며, FAQ의 예시가 free float×3으로 설명된다(float 5% → 상장시총의 15%까지만 인정) |
| 분기 중 임시 조정 존재 | intra-quarter 조정 **폐지**, 분기 리뷰로 일원화 |

### 4.3 2026-06-22 개정 — 순위 산정 기준 변경

- 편입 자격·**순위 산정**은 상장 + **비상장 주식까지 포함한 총 시총** 기준
- **지수 내 비중은 여전히 상장 주식 시총만** 사용 (float-adjusted 아님)
- 배경: 기업의 비상장 존속 장기화, 초대형 IPO, 복수의결권 구조 확산

> **"나스닥100은 시총 기준인가"의 정확한 답**: 그렇다. 단 *순위 판정용 시총*과 *비중 산정용 시총*의 정의가 2026년부터 분리됐다.

### 4.4 비중 상한 (특별 리밸런싱 트리거)

| 단계 | 규칙 |
|---|---|
| 개별 종목 상한 | 20% |
| 집중도 트리거 | 비중 **4.5% 초과** 종목들의 합계가 **48% 이상**이면 → 그 합계를 **40%**로 낮추는 특별 리밸런싱 |
| 개별 특별 트리거 | 단일 종목 24% 초과 시 발동 |
| 증권 단위 | 개별 증권 14%, 상위 5개 증권 합계 38.5% |

### 4.5 Composite / Nasdaq-100 / QQQ

- **Nasdaq Composite** — 나스닥 상장 사실상 전 종목(3,000+), 금융 포함
- **Nasdaq-100 (NDX)** — 그중 비금융(ICB) + 유동성 요건 충족 시총 상위 100
- **QQQ** — NDX를 추종하는 Invesco ETF. 지수가 아니라 상품

### 4.6 최근 편입·편출

| 시점 | 편입 | 편출 |
|---|---|---|
| 2025-12-22 (연례) | ALNY, FER, INSM, MPWR, STX, WDC | BIIB, CDW, GFS, LULU, ON, TTD |
| 2026-06-22 (개정 후 첫 정식 분기 리뷰) | **ALAB, CRWV, NBIS, RKLB, TER** | CHTR, CTSH, **INSM**, VRSK, ZS |

※ 위 6월 명단은 나스닥 IR 보도자료(ir.nasdaq.com)로 교차 확인됨. SPCX는 이 분기 리뷰가 아니라 **Fast Entry로 7월 초 별도 편입**됐다.

※ INSM은 2025-12 편입 → 2026-06 편출. 6개월 만의 재편출로, 분기 리뷰 도입 후 종목 회전이 실질적으로 빨라졌음을 보여준다.
※ 2026-03 분기 리뷰의 세부 명단은 공개 자료에서 미확인 (5/1 개정 직후 과도기).

---

## 5. 실무 함의

### 5.1 섹터 ETF와 지수 섹터 비중이 어긋나는 이유

XLK·XLF·XLY·XLP·XLV·XLE·XLI·XLB·XLU·XLRE·XLC (State Street SPDR)와 Vanguard 섹터 ETF는 **전부 GICS 기준**이다. 나스닥 지수 시리즈는 **ICB 기준**이다.

→ Visa·Mastercard·PayPal은 **XLF(금융 ETF)에 들어 있으면서 동시에 나스닥100(비금융 지수)에도 들어 있다.** 모순이 아니라 서로 다른 분류체계를 쓸 뿐이다.

**"기술섹터 비중"을 볼 때 GICS 기준 수치와 ICB 기준 수치를 혼용하면 반드시 오독한다.** 어느 체계 기준인지 먼저 확인할 것.

### 5.2 어느 체계를 써야 하나

| 분석 대상 | 체계 |
|---|---|
| S&P 500 중심 섹터 로테이션, 팩터 모델, 매크로 데이터 정합 | **GICS** (Bloomberg·FactSet·셀사이드 태그가 전부 GICS 기반) |
| 나스닥100·QQQ, FTSE·STOXX 비교분석 | **ICB** |

**하나의 리포트 안에서 두 체계를 섞지 않는다.** 결제기업처럼 두 체계를 넘나드는 종목이 있으면 벤치마크 기준으로 고정한다.

### 5.3 "AI 관련주"처럼 체계에 없는 테마를 다루는 법

GICS·ICB 어디에도 "AI" 코드는 없다. AI 관련 기업은 반도체(IT)·소프트웨어(IT)·클라우드인프라(IT/통신)·**전력유틸리티**까지 기존 섹터 전반에 흩어져 있다.

1. 공식 분류는 **"무엇을 팔아 돈을 버는가"**를 분류한다. **"무엇에 노출돼 주가가 움직이는가"**는 분류하지 않는다.
2. 테마 분석은 별도 커스텀 바스켓으로 구성하고, GICS/ICB는 그 종목들이 실제로 어떤 매출 구조를 가졌는지 **교차 확인용 보조도구**로 쓴다.
3. MSTR처럼 주가는 특정 테마에 연동되는데 분류상 사업활동과 괴리되는 종목이 반드시 나온다. **테마 노출도와 섹터 라벨을 동일시하지 않는 것**이 오류를 줄이는 핵심.

> 이 프로젝트의 `macro/power-bottleneck-stocks.md`(전력 병목 계층 분류)와 `macro/ai-capex-proxies.md`가 정확히 이 3번을 실행한 문서다. 섹터 체계가 아니라 **병목 근접도 × 대체 불가능성**이라는 자체 축으로 분류했다.

---

## 출처

- [GICS Methodology (MSCI)](https://www.msci.com/indexes/documents/methodology/1_MSCI_Global_Industry_Classification_Standard_GICS_Methodology_20240801.pdf)
- [S&P DJI · MSCI, 2023 GICS 구조 개편 발표](https://www.prnewswire.com/news-releases/sp-dow-jones-indices-and-msci-announce-revisions-to-the-global-industry-classification-standard-gics-structure-in-2023-301515447.html)
- [The New GICS Communication Services Sector (MSCI, 2018)](https://www.msci.com/documents/10199/bbdd3ff9-b66e-975b-d35d-1028d1013837)
- [ICB — FTSE Russell Industry Classification Benchmark](https://classification.codes/classifications/industry/icb)
- [Nasdaq-100 Index Methodology (Nasdaq Indexes)](https://indexes.nasdaq.com/docs/Methodology_NDX.pdf)
- [Nasdaq-100 Methodology Changes FAQ, July 2026](https://indexes.nasdaqomx.com/docs/2026_NDX_Changes_FAQ.pdf)
- [Nasdaq-100 Index Methodology Update: Why Now (Nasdaq)](https://www.nasdaq.com/newsroom/nasdaq100-index-methodology-update-why-now)
- [Nasdaq-100 Inside the Index: PayPal (Nasdaq)](https://www.nasdaq.com/articles/global-indexes/inside-the-index/pypl)

---
*정보 정리 목적이며 투자 권유가 아님.*
