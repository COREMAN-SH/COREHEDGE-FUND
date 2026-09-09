# 재무제표 완전정복 — 트레이딩뷰 Financials 탭 읽는 법

> COREHEDGE COIN 프로젝트 참고자료 · 2026-08-20 작성 / 08-20 개정
> **5장·7장은 TradingView 공식 헬프센터 Financials 카테고리 약 380편을 전수 조사해 반영한 것입니다** — 트레이딩뷰가 각 항목을 실제로 어떻게 정의·계산하는지, 그 정의가 교과서와 어디서 갈라지는지.
> 대상: TradingView 종목 페이지 → **Financials** 탭 (Income statement / Balance sheet / Cash flow)

---

## 0. 한 문장 요약

| 표 | 성격 | 사람으로 치면 | 대답해주는 질문 |
|---|---|---|---|
| **손익계산서** Income Statement | 기간 (동영상) | 연봉 명세서·가계부 | 1년에 얼마 벌고 얼마 남겼나 → **돈 버는 구조인가** |
| **재무상태표** Balance Sheet | 시점 (사진) | 재산 목록 + 대출 잔액 | 지금 뭘 갖고 얼마를 빚졌나 → **버틸 체력이 있나** |
| **현금흐름표** Cash Flow | 기간 (동영상) | 은행 통장 입출금 내역 | 실제 현금이 오갔나 → **거짓말을 하고 있나** |

### 핵심 원리: 이익(Profit) ≠ 현금(Cash)

100억을 **외상으로** 팔면 손익계산서엔 매출 100억이 잡히지만 통장은 0원이고, 재무상태표엔 매출채권 100억이 생깁니다.
→ **흑자인데 망할 수 있다(흑자도산).** 손익계산서만 보면 안 되는 이유.

### 정직도 순위
1. **현금흐름표** — 상대적으로 조작이 어려움 (돈이 들어왔거나 안 들어왔거나). 단 **완전히 안전하진 않음** — 영업비용의 CAPEX 자본화(월드컴), 매출채권 팩토링, 매입채무 지연, CFO/CFI/CFF 재분류로 부풀릴 수 있음
2. **재무상태표** — 중간 (자산 평가에 판단 개입)
3. **손익계산서** — 가장 유연 (수익 인식 시점, 비용 배분 선택지 많음). 하필 뉴스와 주가가 가장 많이 인용하는 표.

---

## 1. 3표의 연결

- 손익계산서 **순이익** → 재무상태표 **이익잉여금**에 누적 (기말 = 기초 + 순이익 − 배당)
- 손익계산서 **순이익** → 현금흐름표 **영업활동의 출발점**
- 현금흐름표 **기말 현금** → 재무상태표 **Cash & equivalents**로 연결 (※ ASU 2016-18 이후 미국기준은 기말 잔액이 **현금+현금성자산+사용제한 현금** 합계라 한 줄과 딱 안 맞을 수 있음 — 주석 조정표 확인)
- 손익계산서 **감가상각비** → 재무상태표 **PP&E** 감소 + 현금흐름표에서 **다시 가산**

**항등식: 자산 = 부채 + 자본** ("굴리는 재산 = 남의 돈 + 내 돈")

### 숫자 예시 (단위 억원)

**손익계산서**: 매출 500 − 매출원가 300 = 매출총이익 200 − 판관비 120(감가상각 20 포함) = 영업이익 80 − 이자 10 = 세전 70 − 법인세 20 = **순이익 50**

**현금흐름표**: 순이익 50 + 감가상각 20 − 매출채권증가 20 + 매입채무증가 10 = **CFO 60** / CAPEX −25 = **CFI −25** / 배당 −15, 차입상환 −5 = **CFF −20** → 순변동 +15, 기초현금 100 → **기말현금 115**

> 순이익 50 < CFO 60 — **CFO가 순이익보다 크다**는 것이 건강한 회사의 기본 모습입니다.

**재무상태표**: 현금 115 + 매출채권 120 + 재고 80 + 유형자산 285 = **자산 600** / 매입채무 90 + 차입금 160 = **부채 250** / 자본금·잉여금 200 + 이익잉여금 150 = **자본 350** → 250 + 350 = 600 ✓

---

## 2. 손익계산서 (Income Statement)

```
매출액                Total revenue
− 매출원가            Cost of goods sold (COGS)
= 매출총이익          Gross profit
− 영업비용            Operating expenses (SG&A / R&D / D&A)
= 영업이익            Operating income (EBIT)   ← 가장 중요한 한 줄
± 영업외손익          Non-operating income (이자·환차·처분손익)
= 세전이익            Pretax income
− 법인세              Taxes
= 당기순이익          Net income
÷ 주식수 = 주당순이익  Basic / Diluted EPS
```

| 항목 | 뜻 | 볼 포인트 / 함정 |
|---|---|---|
| **Total revenue** | 매출액 | YoY 성장률과 추세. 함정: 총액/순액 인식, 채널 스터핑 |
| **COGS** | 매출원가 | 함정: 재고 평가방법 변경으로 원가 조정 |
| **Gross profit** | 매출총이익 | **GPM = 가격 결정력(해자)**. SW 70~90% / 제조 20~40% / 유통 5~20%. 3년 연속 하락 = 해자 붕괴 |
| **Operating expenses** | 판관비 | 매출 증가율 > 판관비 증가율 = 영업 레버리지 작동 (좋음) |
| **R&D** | 연구개발비 | 자본화하면 지금 이익 좋아 보임. 갑자기 줄이면 미래를 판 것 |
| **D&A** | 감가상각비 | 현금 안 나가는 비용. 단 "진짜 비용이 아니다"는 아님 |
| **Operating income** | 영업이익 | **본업 실력. 1순위 지표.** OPM 추세가 핵심 |
| **Non-operating** | 영업외손익 | 영업이익과 순이익 차이가 크면 여기를 펼쳐볼 것 (일회성 이익) |
| **Interest expense** | 이자비용 | **이자보상배율 = 영업이익 ÷ 이자비용. < 1이면 경보** |
| **Taxes** | 법인세 | 실효세율 15~28% 정상. 급변 = 일회성 요인 |
| **Net income** | 당기순이익 | PER의 분모. 비지배지분 제외한 **지배주주 몫** 확인 |
| **Diluted EPS** | 희석주당순이익 | **Basic이 아니라 Diluted를 볼 것.** 격차 10%+ = 심한 희석 |
| **EBITDA** | 상각전영업이익 | 설비 무거운 업종 비교·M&A용. 감가상각 부담 감추는 데 악용됨 |

**3초 지표**: GPM = 매출총이익÷매출 / OPM = 영업이익÷매출 / NPM = 순이익÷매출 / 실효세율 = 법인세÷세전이익

- 최고: 매출↑ + GPM 유지·상승 + OPM이 GPM보다 빨리 개선
- 최악: 매출은 느는데 **영업이익은 제자리** (할인·마케팅으로 매출을 산 것)

---

## 3. 재무상태표 (Balance Sheet)

**유동 = 1년 내 / 비유동 = 1년 초과.** 당장의 생사는 유동자산 vs 유동부채로 판단.

### 자산
| 항목 | 볼 포인트 |
|---|---|
| **Cash & equivalents** | 생존 산소통. **순차입금 = 총차입금 − 현금**. 음수면 순현금 기업 |
| **Accounts receivable** | ⚠️ **매출채권 증가율 > 매출 증가율 = 1급 경고** (미회수/밀어내기/고객 부실). DSO = 매출채권÷매출×365 |
| **Inventories** | ⚠️ **재고 증가율 > 매출 증가율 = 평가손실·할인판매 예고** |
| **Net PP&E** | 유형자산. 크면 고정비 부담 + 진입장벽 |
| **Goodwill** | ⚠️ 인수 프리미엄(시너지·인력 등 잔여가치). **총자산의 30% 초과는 회계 규정이 아니라 주의를 켜는 경험적 기준** — 연쇄 인수 우량기업은 더 높아도 멀쩡함. 진짜 기준은 **인수한 사업부가 계획대로 실적을 내는가** |
| **Other intangibles** | 특허·상표·SW. 기간에 걸쳐 상각 |
| **Deferred tax assets** | 회계·세법의 시점 차이(충당부채·대손·미지급비용·SBC)와 이월결손금에서 생기는 미래 절세 권리. 실현 가능성이 낮아지면 **평가충당금**으로 대규모 상각 |

### 부채
| 항목 | 볼 포인트 |
|---|---|
| **Accounts payable** | 이자 없는 공짜 자금. 협상력 강하면 큰 게 좋음. 단 급증 + CFO 개선 = 대금 미지급으로 짜낸 현금 |
| **Short term debt** | ⚠️ **현금성자산과 직접 비교.** 차환 실패 = 부도 |
| **Deferred revenue** | ✅ 착한 부채. 구독 기업의 **미래 매출 선행지표** |
| **Long term debt** | 전환사채 포함 → 주식 희석 예약 |
| **Operating lease liabilities** | 미국 ASC 842(2018/12/15 이후 개시 회계연도 = 사실상 2019년, 상장사 기준) · IFRS 16(2019/1/1) 이후 임차 약정도 부채. 유통·항공·프랜차이즈 부채비율 급등 요인 |

### 자본
| 항목 | 볼 포인트 |
|---|---|
| **Paid-in capital** | 주주가 넣은 돈. 계속 늘면 유상증자 반복 = 희석 |
| **Retained earnings** | **창업 이래 누적 순이익 − 배당.** 마이너스 = 결손금(누적 적자) |
| **Treasury stock** | 자사주(음수 표시). 단 **빚내서 하는 자사주 매입**은 주의 |
| **Minority interest** | 비지배지분. 크면 "총 순이익 ≠ 내 몫" |

**안정성 지표**
- 유동비율 = 유동자산÷유동부채 → **>150% 양호, <100% 위험**
- 당좌비율 = (현금+단기투자+매출채권)÷유동부채 → **>100%** (약식으로 (유동자산−재고)를 쓰기도 하나 선급금이 남아 과대평가됨)
- 부채비율 = 부채총계 ÷ **자본총계** → 일반 <100%, 제조 <200%
  - ※ 서구권 D/E는 보통 **이자부 차입금 ÷ 자본**이라 숫자가 훨씬 작음. 어느 정의인지 확인하고 비교할 것
- 순차입금/EBITDA → **<2 안전 / 2~3 보통 / 3~4 주의 / >4 위험**

> 은행·유틸리티·리츠는 기준이 완전히 다릅니다. **같은 업종 경쟁사와만 비교하세요.**

---

## 4. 현금흐름표 (Cash Flow)

### ① 영업활동 CFO — 본업으로 번 현금
순이익에서 출발 → 비현금 항목 가산(감가상각, 주식보상비, 손상차손) → 운전자본 변동 조정
- 매출채권 ↑ → 현금 −
- 재고 ↑ → 현금 −
- 매입채무 ↑ → 현금 +

**⚠️ 가장 중요한 비교: CFO vs 순이익**
- CFO > 순이익 → 정상
- CFO < 순이익 3년 연속 → 적신호 (이익이 채권·재고에 갇힘)
- **순이익 사상 최대인데 CFO 감소 → 최고 경고.** 역사상 분식회계 대부분이 이 패턴
- 5년 누적 CFO ÷ 누적 순이익 ≥ 1.0 이면 이익의 질이 좋음

**주식보상비(SBC) 함정**: 현금은 안 나가지만 주주 지분은 진짜로 희석. 매출의 15% 초과 시 CFO를 액면 그대로 믿지 말 것.

### ② 투자활동 CFI
CAPEX(설비), 인수(→Goodwill 급증과 짝), 투자자산 매매, 자산 매각(→영업외이익의 정체).
**CAPEX > 감가상각 = 확장 중 / CAPEX < 감가상각 = 설비 소모 중**

### ③ 재무활동 CFF
차입/상환, 유상증자/자사주, 배당.
**배당 > FCF = 빚내서 배당** (고배당주 필수 확인).

### ④ FCF
```
FCF = CFO − CAPEX
FCF 마진 = FCF ÷ 매출          (10%+ 우수)
FCF 수익률 = FCF ÷ 시가총액     (국채금리와 직접 비교)
```
> 🚨 **트레이딩뷰 화면의 Free Cash Flow는 이 식이 아닙니다.** TV는 총 CAPEX가 아니라 `Capital Expenditures - Fixed Assets`만 뺍니다 → 5장 C절 참조.

### ⑤ +/− 조합 진단표 (이거 하나만 외워도 됨)

| CFO | CFI | CFF | 상태 | 해석 |
|:-:|:-:|:-:|---|---|
| + | − | − | **우량 성숙기업** | 벌어서 투자하고 빚 갚고 배당. 가장 이상적 |
| + | − | + | **성장기업** | 벌지만 투자 기회가 더 커서 조달까지 해 확장 |
| + | + | − | **디레버리징·사업 정리** | 본업으로 **벌면서** 비핵심 자산을 팔아 부채 축소. 대체로 건전. 판 것이 핵심 자산이면 사업 축소 신호 |
| + | + | + | **현금 비축** | 대형 인수 준비 또는 위기 대비. 이유를 찾을 것 |
| − | − | + | **초기 스타트업** | 조달금으로 성장 중. **런웨이**가 전부 |
| − | + | + | 🚨 **최고 위험** | 본업으로 현금을 못 벌면서 자산을 팔고 **동시에 돈까지 빌려** 버팀. 동원 가능한 모든 수단을 쓰는 중 — 8가지 중 가장 위험 |
| − | + | − | ⚠️ **청산 수순** | 돈은 못 벌면서 자산을 팔아 빚을 갚는 중. 채권단 압박으로 사업을 접어가는 모습 |
| − | − | − | ⚠️ **현금 소진 중** | 모든 방향 유출. 단 투자와 부채 상환을 계속한다는 건 **쌓아둔 현금이 크다**는 뜻 — 사이클 저점의 우량기업일 수도. **런웨이**를 먼저 확인 |

---

## 5. 트레이딩뷰 항목 정의의 함정 ⚠️

> 트레이딩뷰 공식 헬프센터 Financials 카테고리 전수 조사(Income 55편 · Balance Sheet 69편 · Cash Flow 46편 · Statistics 124편 등) 결과.

### 대전제: 트레이딩뷰는 원본 수치를 보여주지 않는다

국가·산업·기간을 넘어 비교 가능하도록 **표준화(standardized)한 수치**를 보여줍니다. 트레이딩뷰가 밝힌 이유:

1. "GAAP·SEC·FASB 회계 요건을 감안하더라도 기업에는 **상당한 재량(a great deal of latitude)**이 있다"
2. "공시 방법은 기업과 산업에 따라 매우 다양하다"
3. 회계연도 시작 시점이 다른 기업은 "적절히 처리하지 않으면 비교를 왜곡한다"
4. "많은 국가가 고유한 회계 절차를 갖고 있다"

**→ 트레이딩뷰 숫자가 원본 10-K와 다른 것은 오류가 아니라 설계입니다.** 데이터는 주로 FactSet(섹터·산업 분류도 FactSet 독자 모델), SEC 파일링은 Quartr, 그 외 ICE Data Services.

### A. 손익계산서

| 항목 | 트레이딩뷰의 실제 정의 |
|---|---|
| **Cost of Goods Sold** | ⚠️ **감가상각비(D&A)를 포함**합니다 → 화면의 Gross Profit은 D&A 차감 후 값 |
| **Total SG&A** | ⚠️ **R&D를 포함**합니다. TV가 "출처별 SG&A 차이의 원인이 R&D 포함 여부"라고 직접 명시. R&D 제외분은 `SG&A, Others` |
| **Total Operating Expenses** | ⚠️ `= Total SG&A + COGS` — **매출원가를 포함**. TV 스스로 "다른 출처는 SG&A만 세기 때문에 숫자가 다르다"고 경고.<br>반면 `Operating Expenses (excl. COGS) = Total SG&A + Other Operating Expenses` — **이름 비슷한 두 필드의 정의가 다름** |
| **Operating Income vs EBIT** | ⚠️ **다른 값입니다.** TV 명시: "EBIT는 Operating income으로도 불리나 항상 동일하지는 않다"<br>`Operating Income = Gross Profit − Operating Expenses (excl. COGS)`<br>`EBIT = Total Revenue − COGS − SG&A − Other Operating Expenses`<br>`EBITDA = EBIT 산식 + D&A` |
| **Net Income** | TV는 "**우선주 배당까지 지급한 후**"로 정의 (표준 정의와 다름). 단 `Diluted Net Income Available to Common = Net Income + Dilution Adjustment − Preferred Dividends`로 또 빼고 있어 문서상 모순 존재 |
| **Unusual Expenses** | 일회성 비용은 **Non-Operating Income에 들어감** → TV의 **Operating Income에는 일회성이 안 섞임**(장점). 하위: Impairments / Restructuring charge / Legal claim expense / Unrealized gain-loss / Other exceptional charges |
| **Dilution Adjustment** | TV 고유 항목. 전환증권이 전부 전환될 때의 **최대 이익 감소분** |
| **Reported EPS vs Standardized** | Reported = 회사 보도자료에서 직접 수집(비표준 조정 포함). Standardized = 완전희석 GAAP EPS. **둘은 다를 수 있음** |

**은행·보험은 Gross profit · EBITDA · EBIT이 아예 없습니다** (COGS·SG&A가 없어서). 대신:
```
Net Revenue = 순이자수익(Net Interest Income) + 비이자수익
Net Interest Income = 이자수익 − 이자비용
Net Revenue After Provisions = Net Revenue − 대손충당금 전입 (IFRS 9 기대신용손실)
```
※ 은행 매출 정의는 국가마다 다름(인도 등은 Total revenue) → **국가 간 P/S 비교 무의미**

**분기 데이터가 없는 항목(연간만)**: Depreciation · Amortization · **Impairments** · **Restructuring charge** · Legal claim expense · Unrealized gain/loss · Other exceptional charges · 세부 법인세 항목 전체
→ **손상차손·구조조정비는 분기 추적 불가**

### B. 재무상태표

| 항목 | 트레이딩뷰의 실제 정의 |
|---|---|
| **Total Equity** | ⚠️ `= Shareholders' Equity + Minority Interest` — **비지배지분 포함**. 지배주주 기준은 `Common Equity, Total` |
| **Total Debt / Long Term Debt** | ⚠️ **운용리스부채 포함** (단기 쪽엔 파생부채·무이자대출·무라바하 금융까지). 순수 차입금은 `Long Term Debt Excluding Lease Liabilities` |
| **Net Debt** | ⚠️ `= Total Debt − Cash & **Short Term Investments**` — 단기투자까지 차감해 일반 정의보다 작게 나옴 |
| **Cash & Equivalents** | 만기 3개월 이하 + **유동 사용제한 현금(restricted cash) 포함** → 유동성이 실제보다 좋아 보임. `Short Term Investments`는 "3~12개월" |
| **Net Intangible Assets** | ⚠️ **Goodwill 포함**. 영업권 제외분은 `Net Other Intangibles`.<br>`Tangible BPS = (Common equity − Intangible assets) / Common shares` — 영업권까지 전부 차감 |
| **Paid in Capital** | ⚠️ `= Common Stock Par + APIC + **Treasury Stock**` — 자기주식이 납입자본 안에 들어 있음 |
| **Accounts Receivables, Net** | 범위가 넓음 — 공사 진행청구액·유보금·모회사/자회사/지분법 채권 포함 (건설·조선업 주의) |
| **Other ~ 전부** | "A를 제외한 나머지"로 정의된 **잔여 계정**. 원 재무제표와 1:1 대응 안 함 |
| **Total Assets / Liabilities** | 유동/비유동 구분은 **"for commercial companies"에만** 적용. 금융업 대체 구조는 문서화 없음 |

### C. 현금흐름표 — 가장 큰 함정

**🚨 트레이딩뷰의 Free Cash Flow는 일반적 FCF가 아닙니다**

```
TV 공식:  Free cash flow = CFO − Capital Expenditures - Fixed Assets
                                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Total이 아님!
```
`Capital Expenditures - Other Assets`에는 **무형자산 취득 · 개발비 자본화 · 탐사평가자산 · 이연비용**이 들어 있고 이게 차감되지 않습니다.
→ **소프트웨어 자본화가 큰 기업, 광업·에너지 기업에서 TV의 FCF가 구조적으로 크게 나옵니다.**
→ 직접 계산: `진짜 FCF = CFO − Capital Expenditures, Total`

| 항목 | 트레이딩뷰의 실제 정의 |
|---|---|
| **CFO** | 공시 총계를 그대로 안 쓰고 **재구성**: `Funds from Operations + Extraordinary Item + Changes in Working Capital`<br>`Funds from Operations = Net Income + D&A + Deferred Taxes + Non-Cash Items` |
| **Extraordinary Item** | ⚠️ **중단영업 처분손익 · 보험금 · 소송 합의금이 영업활동 안에** 들어감 → 해당 이벤트가 있던 해엔 CFO·FCF가 일회성으로 왜곡 |
| **Non-Cash Items** | ⚠️ 이름과 달리 **"이자 지급·수취", "법인세 납부·환급"**이 첫 두 항목. 실질은 기타 조정 잔여 버킷 |
| **주식보상비(SBC)** | ⚠️ **현금흐름 문서 46편에 단어가 한 번도 안 나옴.** 분리 추적·FCF 조정 불가. 테크 기업 FCF는 SBC를 더한 상태 그대로 |
| **리스 상환** | ⚠️ 역시 한 번도 언급 없음 → **리스 많은 업종(유통·항공·통신) FCF 과대 위험** |
| **Net Income (Cash Flow)** | TV 명시: **"손익계산서 순이익과 반드시 일치하지 않을 수 있다"** |
| **Issuance (Retirement) of Stock, Net** | ⚠️ 전환사채→보통주 같은 **비현금 전환이 섞임**. 게다가 "장부가액의 순변동"으로 정의 → **자사주 매입 규모로 읽으면 안 됨** |
| **Purchase/Sale of Business** | M&A 라인이 아니라 **처분 전반** 라인 (단순 PP&E 처분 포함). 반대로 소수지분 취득(재무 성격)이 투자활동에 들어감 |
| **Common Dividends Paid** | REIT 분배금·파트너십 분배금·하이브리드 분배금·RSU 배당등가금까지 포함 |

### D. 화면 사용설명서

- **접근**: Supercharts → `Indicators, metrics, and strategies` → **Financials 탭** (Income Statement / Balance Sheet / Cash Flow / **Statistics**). 기간은 **FY / FQ / TTM**
- **유럽 종목은 분기가 비어 있는 게 정상**: 분기 보고=인도·폴란드 / 반기=오스트리아·벨기에·프랑스·독일·스위스 / 혼재=이탈리아·러시아·싱가포르·스페인·영국
- **실적 서프라이즈 색이 나중에 바뀔 수 있음**: TV 명시 "컨센서스 예측치는 실제 실적이 나온 뒤에도 갱신될 수 있다". E 아이콘 🟢beat / 🔴miss / ⬜0 또는 없음 / 🩷미래
- **실적일 '≈'는 추정**: 패턴 없는 기업은 "보고기간 종료 +1개월의 수요일"로 임의 설정, 지나면 **매일 하루씩 롤포워드**
- **GAAP vs non-GAAP**: 재무제표는 GAAP, earnings·revenue만 non-GAAP 병행. 미보고 시 **추정치 중앙값** 사용. 추정 방법론도 지역별 상이 — **유럽=adjusted EPS, 아시아=reported EPS**. 은행은 EBITDA·FCF 추정치 없음
- **TV가 문서화하지 않은 것**: ① 비달력 회계연도의 "FQ1"이 몇 월인지 ② 표시 통화 규칙 ③ 소급 재작성 처리 ④ 히스토리 기간 — **네 가지 모두 공식 문서 없음**. 확인된 것: 시가총액 히스토리는 2016년부터
- **은행에서 계산되지 않는 지표 8개**(TV 명시): Quick ratio · Cash to debt ratio · COGS to revenue ratio · Inventory turnover · Inventory to revenue ratio · Days inventory · Days payable · Days sales outstanding. **Cash conversion cycle**도 재고 의존 섹터에만 적용

---

## 6. 기업 체력 4축

**수익성** — GPM / **OPM(1순위)** / ROE(15%+) / ROA / **ROIC > WACC(8~10%)**
```
ROE = 순이익 ÷ 자본총계        ROA = 순이익 ÷ 총자산
NOPAT = 영업이익 × (1 − 실효세율)
ROIC  = NOPAT ÷ (순차입금 + 자본총계)
```

듀폰: `ROE = 순이익률 × 자산회전율 × 재무레버리지`
- 순이익률로 높다 → 최고 (브랜드·특허)
- 자산회전율로 높다 → 좋음 (유통형)
- **레버리지로 높다 → 주의** (금리·불황에 급전직하)

**안정성** — 유동비율 / 당좌비율 / 부채비율 / **이자보상배율(>3, <1이 3년 = 한계기업)** / 순차입금·EBITDA / 런웨이

**효율성**
```
DIO = 재고     ÷ 매출원가 × 365   (분모가 매출원가)
DSO = 매출채권 ÷ 매출     × 365   (분모가 매출)
DPO = 매입채무 ÷ 매출원가 × 365   (분모가 매출원가)
CCC = DIO + DSO − DPO
```
**CCC가 음수면 최고** (남의 돈으로 사업. 코스트코·애플형)

**성장성** — 매출 CAGR / **영업이익 성장률 > 매출 성장률** / EPS 성장(주식수 감안) / FCF 성장

> **좋은 회사 프로필**: OPM 15%+ · ROIC 12%+ · 순차입금/EBITDA <2 · CCC 짧음 · 매출 CAGR 10%+ · CFO > 순이익 · FCF마진 10%+ · 주식수 감소

---

## 7. Statistics 탭 공식 계산식

> 같은 이름의 지표라도 평균/기말, 분모가 매출/매출원가, 주식수 기준이 달라집니다. TV는 이 기준이 **일관되지 않습니다.**

### 수익성
| 지표 | TV 계산식 | 주의 |
|---|---|---|
| Gross / Operating / EBITDA / Net margin | 각 이익 ÷ Revenue × 100 | EBITDA margin은 은행·보험 미제공 |
| **Return on equity** | `Net income / **평균** Total shareholders' equity` | ⚠️ 기말 아님. 분기는 분자에 **LTM 순이익** |
| **Return on assets** | `Net income **before discontinued operations** / 평균 총자산` | ⚠️ 분자가 일반 순이익 아님 |
| Return on common equity | `(Net income before disc.ops − 우선주배당) / 평균 보통주자본` | **지배주주 기준으로 볼 때 이걸 쓰세요** |
| Return on invested capital | `Net income / 2기간 평균 투하자본` | |
| Return on capital employed % | `Operating income / (평균 총자산 − 평균 유동부채)` | 분기·반기는 TTM 영업이익 |
| Return on total capital % | `Operating income / 평균 총자본 × 100` | ⚠️ **TV 평균 산식이 통상 평균의 2배** (문서 오류) |
| Sustainable growth rate | `ROE(평균자본) × (1 − 배당성향/100)` | ROE 20%·배당성향 30% → 14% |
| SG&A expenses ratio | `SG&A (**R&D 제외**) / Total revenue` | Total SG&A와 다름 |
| Quality ratio | (계산식 미공개) | ⚠️ 식 없음 |

### 유동성·안정성
| 지표 | TV 계산식 | TV 기준 / 주의 |
|---|---|---|
| Current ratio | 유동자산 / 유동부채 | TV는 임계값 제시 안 함 |
| **Quick ratio** | `(유동자산 − 재고) / 유동부채` | ⚠️ **약식** — 선급금이 남아 실제보다 좋게 나옴. **은행 미제공** |
| Cash ratio | 현금+단기투자 / 유동부채 | ✅ **TV: 1 이상이면 양호** |
| Debt to equity ratio | (계산식 미공개) | ⚠️ 분모 Total Equity에 **비지배지분 포함** |
| Net debt to EBITDA | Net debt / EBITDA | 분기는 TTM EBITDA. EBITDA 음수면 계산 불가 |
| **Interest coverage** | `**Operating income** / Interest expense` | ⚠️ EBIT 아님. TV에서 둘은 다른 값 |
| EBITDA less capex interest coverage | (원문에 EBITDA interest coverage 식이 복사돼 있음) | ⚠️ **capex 차감 식이 문서에 없음** |
| Effective interest rate on debt | `Interest expense / 평균 debt` | 실효 조달금리 |
| Tangible common equity ratio | `(총자본 − 무형 − 우선주) / (총자산 − 무형)` | 금융회사 레버리지용 |

### 효율성
| 지표 | TV 계산식 | 주의 |
|---|---|---|
| **Days sales outstanding** | `매출채권(기말) / **Revenue** × 일수` | ⚠️ 평균 아님. 은행 미제공 |
| **Days inventory** | `**평균** 재고 / COGS × 일수` | DSO와 기준이 다름. 은행 미제공 |
| **Days payable** | `매입채무(기말) / COGS × 일수` | ⚠️ 평균 아님. 은행 미제공 |
| Inventory turnover | `COGS / 기말 재고` | ⚠️ 본문은 "2기간 평균"이라 서술 — **모순** |
| **Cash conversion cycle** | (계산식 미공개) | ⚠️ 구성요소의 평균/기말 기준이 서로 달라 **직접 계산값과 화면값이 다를 수 있음** |
| Asset / Fixed asset / Receivables turnover | Revenue ÷ 2기간 평균 (자산 / Net PP&E / 매출채권) | 분기는 TTM 매출 |
| per-employee 8종 | 각 항목 ÷ 직원 수 | 연간 기준 |

### 밸류에이션
| 지표 | TV 계산식 | TV 기준 |
|---|---|---|
| Market capitalization | 총발행주식수 × 종가 (자기주식 제외) | Large>$10B / Mid $2~10B / Small $300M~$2B. **히스토리 2016년부터** |
| **Enterprise value** | `종가 × **희석**주식수 + 우선주 + Total debt + 비지배지분 − 현금&단기투자` | ⚠️ EV는 희석주식수, 시총은 총발행주식수 → **EV − 순부채 ≠ 시총** |
| P/E | `주가 / **Diluted EPS TTM**` | |
| **Operating earnings yield %** | `희석 순이익 / 시가총액` | ⚠️ **이름과 식 불일치** — 교과서(EBIT/EV)와 완전히 다름 |
| P/FCF | `종가 × **Common** shares / FCF` | 주식수 기준이 지표마다 다름 |
| P/Cash | `종가 / (현금&단기투자 ÷ **Diluted** shares)` | |
| PEG | `Price / EPS / EPS growth` | ✅ **TV: 1 미만이 good** |
| EV/EBITDA | EV / EBITDA | ✅ **TV: 10 미만이 normal** |
| NCAVPS | `(유동자산 − **총부채** − 우선주) / 보통주식수` | ✅ **TV: 주가 ≤ NCAVPS × 67%면 bargain** |
| Tobin's Q | `Market value / Total assets` | TV: **"Q>1이 반드시 고평가는 아니다"** |
| Graham's number | `√(22.5 × EPS × BPS)` | EPS 종류를 TV가 명시 안 함 |

### 배당
| 지표 | TV 계산식 | TV 기준 |
|---|---|---|
| Dividend yield | `TTM 배당(**특별배당 제외**) / 주가` | |
| Dividend payout ratio | `DPS(**extra 포함**) / EPS × 100` | ⚠️ 배당수익률과 **기준이 정반대**. ✅ **100% 이상 = 경고** |
| Cash dividend coverage ratio | `CFO / Common dividends paid` | ✅ **>1 충분 / <1 의존** |
| Buyback yield | `자본금 변동액 / 시가총액 × 100%` | ⚠️ 현금흐름표상 매입액이 아님 |
| Continuous dividend growth / payout | 연속 증가 햇수(1~7) / 연속 지급 햇수(1~8) | ⚠️ **정수 상한 있음** — 배당귀족 판별 불가 |

### 점수 모델 (스크리너 필드로 직접 제공)
| 모델 | TV 판정 기준 | 내용 |
|---|---|---|
| **Altman Z-score** | **>3.00 안전 / <1.81 위험** | `1.2·(순운전자본/자산) + 1.4·(이익잉여금/자산) + 3.3·(EBIT/자산) + 0.6·(자기자본 시가/총부채) + 1.0·(매출/자산)`<br>※ TV 명시: **제조업 전용 설계, 표본에서 서비스업·은행 제외** |
| **Piotroski F-score** | **8~9 우량 / 0~2 취약** | 9항목 각 1점: 순이익>0, CFO>0, ROA 개선, **CFO>순이익**, 장기차입 하락, 유동비율 상승, **신주 발행 없음**, 매출총이익률 상승, 자산회전율 상승 → **이 문서 체크리스트의 압축판** |
| **Beneish M-score** | **>−1.78이면 조작 가능성** | 8변수. DSRI(매출채권/매출 변화)·GMI·SGI·TATA((계속영업이익−CFO)/자산)가 핵심<br>※ TATA 계수가 통상 4.679가 아니라 **4.697**로 적혀 있음 |
| **Sloan ratio** | **−10%~+10% 안전** | `(순이익 − CFO − CFI) / 총자산`. 투자활동까지 차감하는 점이 특이 |
| **Accruals** | 큰 양수 지속 시 검증 | `순이익 − CFO`. **비율이 아니라 금액**이라 기업 간 비교 불가 |
| Springate score | **>0.862 안정** | 4변수 Altman 파생 |
| Zmijewski score | 높을수록 위험 | 수익성·레버리지·유동성 3변수. TV가 임계 수치 미제시 |
| Fulmer H factor | **>0 안정 / <0 곤경** | 9변수. ※ X9가 원논문 log(EBIT/이자)이 아니라 log(EBIT)/이자로 표기 |
| KZ index | 높을수록 외부자금 의존 | **금융환경 악화 시 먼저 힘들어질 기업** 필터 |

> **실전**: 종목 하나에 **Piotroski F ≥ 8**과 **Altman Z ≥ 3**만 먼저 보면 부실기업 대부분이 걸러집니다. **Beneish M ≤ −1.78**과 **Sloan ratio ±10% 이내**를 더하면 이익의 질까지 커버. 단 Altman Z는 제조업 모델임을 감안하세요.

### TradingView 문서 자체의 오류·공백 (확인된 것)
- **EBITDA less capex interest coverage** — capex 차감 식이 문서에 없음(다른 식이 복사됨)
- **Shares buyback ratio** — 괄호가 깨진 식
- **Inventory turnover** — 식(기말)과 본문(평균)이 모순
- **Return on total capital** — 평균 산식이 통상 평균의 2배
- **계산식이 아예 없는 항목 26개** — Debt to equity ratio, Cash conversion cycle, Quality ratio, Forward P/E·P/S, Beta, Free float, 주식수 3종, **성장률(Growth %) 계열 10종 전부**
- **성장률 지표가 두 벌 존재** — 구버전(식 있음) vs 신버전(식 없이 Annual YoY / Quarterly YoY / TTM YoY / QoQ 4변형만)

---

## 8. 살까 말까 — 밸류에이션 + 체크리스트

| 지표 | 계산 | 출처 | 쓰임 / 함정 |
|---|---|---|---|
| PER | 주가÷EPS | 손익 | 이익이 왜곡되면 통째로 무의미. 사이클주는 낮을 때가 고점 |
| PBR | 주가÷BPS | 재무상태 | 은행·철강·조선 등 실물자산 업종에 유효 |
| **EV/EBITDA** | EV ÷ EBITDA<br>EV = 시총 + 총차입금 − 현금 **+ 우선주 + 비지배지분** | 3표 | **업종 내 비교에 가장 공정** |
| **P/FCF** | 시총÷FCF | 현금흐름 | **회계 조작에 가장 강함.** FCF수익률을 국채금리와 비교 |
| PSR | 시총÷매출 | 손익 | 적자 성장주용. 마진 개선 경로 확인 필수 |
| PEG | PER ÷ EPS성장률(%)<br>예: PER 20, 성장 15% → 20÷15 = 1.3 | 손익 | <1이면 저평가라는 통설. **성장률에 0.15가 아니라 15를 넣을 것.** 보통 향후 3~5년 예상 EPS 성장률 |
| 배당수익률 | DPS÷주가 | 현금흐름 | 유난히 높으면 삭감 임박 신호. FCF÷배당 > 1.5 확인 |

**비교 원칙**: ① 같은 업종끼리만 ② 그 회사의 과거 5~10년 밴드와 ③ 지표 하나로 결론 내지 않기

### 매수 전 12문항 (9개 이상 Yes면 재무적 통과)
1. 매출이 3년 연속 성장했는가
2. 영업이익률이 유지·개선되는가
3. CFO > 순이익인가 (3년 평균)
4. FCF가 플러스이고 성장하는가
5. 매출채권 증가율 < 매출 증가율인가
6. 재고 증가율 < 매출 증가율인가
7. 순차입금/EBITDA < 3인가 (2 미만 안전 / 3~4 주의 / 4 초과 위험)
8. 이자보상배율 > 3인가
9. 유동비율 > 100%인가
10. ROE 10~15%+ 이고, 과도한 레버리지가 아니라 마진·회전율에서 나온 것인가 (ROE−ROA 격차로 확인)
11. 희석 발행주식수가 늘지 않았는가
12. Goodwill 비중이 과도하지 않은가 (총자산의 30%가 주의 신호 — 높다면 인수 사업부 실적 확인)

> **지름길**: 트레이딩뷰의 **Piotroski F-score**는 이 12문항 중 9개를 자동 점수화한 것입니다. F-score 8 이상이면 상당 부분 통과한 셈.
>
> 이 리스트는 **"망하지 않을 회사인가"** 필터입니다. **"오를 주식인가"**는 밸류에이션 + 산업 사이클 + 경쟁 구도를 더해야 나옵니다.

---

## 9. 빨간 깃발

**1급 (즉시 손 떼기)**
- 순이익↑ 인데 CFO↓ ← 최강 경고 신호
- 매출채권·재고가 매출보다 훨씬 빠르게 증가
- 이자보상배율 < 1 지속
- 감사의견 한정 / 회계법인 잦은 교체

**2급 (이유 확인 필수)**
- 매년 반복되는 '일회성' 비용 → GAAP 순이익 기준으로 볼 것
- Goodwill 급증 후 성장 정체 → 손상차손 예고
- Other 항목이 총액의 5~10% 초과
- 매입채무만 급증하며 CFO 개선
- 실효세율 급변
- 유상증자·CB 반복 발행
- 매출채권 팩토링·유동화, SPC·조인트벤처, 매입채무 금융(reverse factoring)으로 부채 은닉 — **총차입금은 그대로인데 금융·수수료성 비용만 증가**
  - ※ 2019년 이후 운용리스는 재무상태표에 잡히므로 "리스로 부채 숨기기"는 옛날 이야기
- 사업부문 잦은 재분류
- SBC가 매출의 15% 초과
- 배당 > FCF

> **원칙: 현금흐름표와 손익계산서가 다른 말을 하면, 먼저 현금흐름표 쪽을 확인하라.**
> 회계 규칙은 이익을 만들 여지를 크게 남기므로 CFO가 대체로 더 정직합니다. 다만 CFO도 ⓐ 영업비용의 CAPEX 자본화(월드컴 분식은 CFO를 오히려 **좋아 보이게** 만들었습니다) ⓑ 매출채권 팩토링·유동화 ⓒ 매입채무 지연 ⓓ CFO/CFI/CFF 재분류로 부풀릴 수 있습니다.
> **교차 확인: CFO 개선과 CAPEX 급증이 동시에 나타나면 비용의 자본화를 의심하세요.**

---

## 10. 트레이딩뷰 10분 스캔 루틴

| 분 | 화면 | 확인 |
|---|---|---|
| 0–2 | Income statement · Annual | Total revenue / Operating income 5년 막대 우상향? 영업이익이 매출보다 빨리 크는가 |
| 2–3 | Income statement · Quarterly | 최근 4~8분기 추세 (연간은 좋은데 최근 분기 꺾임?) |
| 3–5 | Cash flow | CFO > 순이익? FCF 플러스? CFO/CFI/CFF 부호 조합 |
| 5–7 | Balance sheet | 현금 vs 총차입금 / 단기차입금 vs 현금 / 매출채권·재고 증가율 / Goodwill 비중 / 이익잉여금 |
| 7–8 | Statistics 탭 | 마진·ROE·ROA·부채비율 **시계열 기울기** |
| 8–9 | Statistics 점수 모델 | **Piotroski F ≥ 8** · **Altman Z ≥ 3** · **Beneish M ≤ −1.78** · **Sloan ratio ±10%** — 네 숫자로 부실기업과 이익의 질을 한 번에 필터 |
| 9–10 | Overview | PER·EV/EBITDA·PBR·배당수익률을 업종·과거 밴드와 비교 |

**팁**: 항목명을 클릭하면 차트에 시계열로 그려짐 / Annual·Quarterly·**TTM** 전환 / ▸로 하위 항목 펼치기 / YoY % 표시 켜기 / 경쟁사를 다른 탭에 나란히

---

## 11. 업종별 차이

| 업종 | 핵심 지표 | 주의 |
|---|---|---|
| 은행·보험 | **Net revenue**, CET1 비율, 대손충당금, NPL, Tangible common equity ratio | 부채비율 1,000% 정상. 충당금 축소로 이익 만들기 함정.<br>TV: 은행은 Gross profit·EBITDA·EBIT **미제공**. Basel III 최소 — **CET1 ≥ 4.5% / Tier1 ≥ 6.0% / Total capital ≥ 8%** (÷RWA). 은행 매출 정의가 국가마다 달라 **국가 간 P/S 비교 무의미** |
| 리츠·부동산 | **FFO = 순이익 + 부동산 감가상각 − 부동산 처분손익** / AFFO(FFO − 유지보수 CAPEX 등, 배당 지속성 판단) | 감가상각이 커서 PER 무의미 |
| 바이오 | **런웨이 = 현금 ÷ 분기 소진액**, R&D, 파이프라인 | 매출·이익 없는 게 정상. 12개월 미만 = 증자 임박 |
| SW·SaaS | 선수금, GPM(70~85%), SBC 비중, **Rule of 40 = 매출성장률(%) + FCF마진(또는 영업이익률)(%) ≥ 40** | GAAP 적자·조정 흑자 흔함. GAAP으로도 확인 |
| 반도체·중공업 | CAPEX 사이클, 가동률, 수주잔고 | **PER 낮을 때가 고점**인 경우 많음 → PBR·사이클 위치로 |
| 유통·소비재 | 재고회전, **CCC**, 동일점포매출 | CCC 음수면 최고. 리스부채가 부채비율 키움 |
| 통신·유틸 | EBITDA, 순차입금/EBITDA, 배당 커버리지 | 금리 상승기 직접 타격 |
| 항공·해운 | 리스 포함 순차입금, 유가 헤지, 가동률 | 고정비 극단적 → 매출 소폭 감소에도 급적자 |

---

## 12. 코인 관련주 특수편

### ⚠️ FASB ASU 2023-08 — 2024/12/15 이후 개시 회계연도부터 적용
보유 암호자산을 **공정가치(시가)로 평가**하고 **평가손익을 순이익에 반영**.
이전에는 무형자산 손상 모델이라 **하락은 즉시 반영, 상승은 미반영**이던 비대칭 구조 → **전환 전후 실적은 직접 비교 불가.**
⚠️ **조기 적용이 허용**되어 회사마다 전환 연도가 다릅니다(일부 대형 보유 기업은 FY2024부터 적용). 두 회사의 2024년 실적을 비교할 땐 각 사의 채택 시점을 확인하세요.
⚠️ 이 기준은 **회사가 직접 발행한 토큰**이나 **다른 자산에 대한 청구권을 담은 토큰**(일부 랩드 토큰·NFT 등)에는 적용되지 않습니다.
결과: 코인 보유 기업의 순이익이 분기마다 코인 시세대로 요동. 이 손익은 현금이 아니므로 CFO에서 다시 차감/가산됨.
→ **이런 기업일수록 손익계산서보다 현금흐름표·재무상태표가 훨씬 중요.**

### ① 거래소 (COIN 등)
- **거래 수수료 매출 vs 구독·서비스 매출 비중** ← 최우선. 후자 비중 상승 = 체질 개선
- 비용의 대부분이 고정비 → 거래량 감소 시 급격히 적자
- **고객 예치 암호자산은 회사 돈이 아님** (자산·부채 동시 계상). 자사 보유분과 구분
- 순현금 포지션 = 하강 사이클 생존력
- 밸류: 사이클 정점 이익 기준 PER 10은 실제로 PER 40일 수 있음

### ② BTC 보유 기업 (MSTR / Strategy 등)
- 본업 매출·영업이익은 사실상 무의미
- 실제로 볼 것: **보유 BTC 수량 · 평균 취득단가**
- 순이익은 BTC 시세로 요동 → **PER 무의미**
- **핵심 위험: 자금 조달 구조.** 전환사채·유상증자·우선주로 조달해 BTC 매수
  - 확인: CB 만기 시점 / 전환가 / 이자 부담 / **발행주식수 증가 속도** / **주당 BTC 보유량 추이**
- **mNAV** >1이면 프리미엄. 프리미엄 유지 중엔 증자가 주주에 유리, **1 아래로 꺼지면 구조 역전**
  - `시총 기준 = 시총 ÷ BTC 가치` / `EV 기준 = (시총 + 부채 + 우선주 − 현금) ÷ BTC 가치`
  - ⚠️ 시총 기준만 보면 **빚 많은 회사가 오히려 싸 보입니다.** 두 값의 차이가 곧 이 회사에 걸린 레버리지
- 본질: 사업체보다 **레버리지 걸린 BTC 보유 수단**. 하락기엔 부채 압박으로 BTC보다 더 빠질 수 있음

### ③ 채굴 기업 (MARA / RIOT / CLSK 등)
- **매출원가 = 전기료.** 1 BTC당 채굴 현금원가 < BTC 가격이어야 생존. 전력 계약 단가가 해자
- 감가상각이 매우 큼 (채굴기 수명 2~4년, 진짜 재구매 필요) → **이 업종에서 EBITDA는 특히 위험한 지표**
- 난이도 상승 → 지속 CAPEX 없으면 점유율 소멸 → **FCF 만성 마이너스가 구조적 특성**
- **반감기**: 약 4년마다 채굴 보상 절반
- **캔 BTC 보유(HODL) vs 즉시 매도** 전략에 따라 재무제표 모양이 완전히 달라짐
- ⚠️ **ATM 상시 유상증자.** 발행주식수 연 20~50% 증가도 흔함 → **Diluted shares outstanding 5년치 필수 확인**

### 트레이딩뷰의 코인 자체 지표 (기업 재무와 별개)

⚠️ **트레이딩뷰 헬프센터에는 기업 재무상태표의 암호자산 회계 처리에 대한 문서가 하나도 없습니다.** Crypto 폴더 63편은 전부 코인 자체의 온체인·시장·소셜 지표입니다. 제공자도 Glassnode·Coinmetrics·LunarCrush·DefiLlama로 각각 다르며, TV는 "지표마다 제공자가 다를 수 있다"고 명시 → **지표끼리 직접 비율 계산은 위험.**

| 지표 | 계산식 | 해석 |
|---|---|---|
| **NVT** | 시가총액 ÷ USD 트랜잭션 볼륨 | 코인판 PER. 상승 추세=고평가, 하락 추세=저평가 |
| **Velocity** | USD 온체인 볼륨 ÷ 시가총액 **= 1/NVT** | ⚠️ NVT의 역수 — 둘을 같이 필터링하면 같은 조건을 두 번 거는 것 |
| **Market cap / TVL** | 시총 ÷ TVL | TV: **0에 가까우면 저평가, 1.0 초과면 고평가 시사** |
| **Volume / Market Cap** | 24h 거래량 ÷ 시총 | 유동성. ⚠️ 극단적으로 높으면 **wash trading 신호** |
| **FDV** | 최대 발행량 × 현재가 | 시총과의 격차 = **향후 언락 매도압력** |
| **In the money addresses %** | 평균 매수가 < 현재가인 주소 비중 | ⚠️ TV 경고: 지나치게 높으면 **차익실현 매물로 하방 압력** |
| **Rank** | (시총 정렬 아님) | ⚠️ 내부 가중치가 적용돼 stETH·WBTC 강등 → **CoinGecko/CMC 순위와 다름** |
| Galaxy Score / AltRank | LunarCrush 소셜 지표 | ⚠️ TV는 **높은 게 좋은지 낮은 게 좋은지 정의하지 않음** |

### 공통 원칙
1. 순이익·PER을 믿지 말 것 (코인 평가손익이 섞임)
2. **현금흐름표(CFO·CFF)와 발행주식수**가 진짜 정보
3. 사이클 위치를 항상 의식 — 강세장 실적으로 만든 밸류에이션은 하강기에 3~5배 악화
4. 셋 다 결국 **BTC 가격에 대한 레버리지 베팅** — 분산이 아니라 집중

---

## 마지막

재무제표는 **과거의 기록**이고 주가는 **미래의 기대**를 반영합니다.
재무제표로 할 수 있는 일은 "망하지 않을 만큼 튼튼한가", "지금까지 어떻게 벌어왔는가"의 확인이고,
**그 다음이 산업·경쟁·사이클에 대한 판단**입니다. 순서를 거꾸로 하지 마세요.

---
*본 문서는 회계·재무 개념 학습 자료이며 특정 종목에 대한 투자 권유가 아닙니다.*

---

**출처**: 5장·7장 및 각 장의 「TV」 표시 내용 — [TradingView Help Center · Financials](https://www.tradingview.com/support/categories/financials/) 전수 조사 ([Income Statements](https://www.tradingview.com/support/folders/43000565035-income-statements/) 55편 · [Balance Sheet](https://www.tradingview.com/support/folders/43000565036-balance-sheet/) 69편 · [Cash Flow](https://www.tradingview.com/support/folders/43000565037-cash-flow/) 46편 · [Statistics](https://www.tradingview.com/support/folders/43000572993-statistics/) 124편 · [How to read financial statements](https://www.tradingview.com/support/solutions/43000760059-how-to-read-financial-statements/) · Overview · Key data points · Crypto)<br>회계기준 — [Grant Thornton — ASU 2023-08](https://www.grantthornton.com/insights/articles/audit/2023/snapshot/december/clarifies-accounting-for-certain-crypto-assets) · [PwC Viewpoint — ASC 350-60](https://viewpoint.pwc.com/dt/us/en/pwc/accounting_guides/crypto-assets-guide/crypto_assets_guide/ch2_holding_crypto_assets/24_crypto_assets_accounted.html) · [FASB ASU 2023-08 원문](https://storage.fasb.org/ASU%202023-08.pdf)
