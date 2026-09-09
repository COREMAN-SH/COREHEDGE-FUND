# 유입 멀티플 모델 — 채널 종합 유입 대비 BTC 시총 반응

> 최초 작성: 2026-09-07 · 검증 구간: 2026-07-31 ~ 09-04
> 관련: `macro/us-crypto-etf-flows-2026-09-01.md` · `macro/stablecoin-netflow-2026-08-25.md` · `framework/liquidity-gauges-guide.md` · `framework/perp-basis-regime-2026-09-01.md`

## 0. 한 줄

**"$1 들어오면 시총 k달러" 형태의 멀티플은 상수로 존재하지 않는다.** 2026년 8월 실측이 그 반증이다 — 측정 가능한 순유입은 **−$4.1B(순유출)**인데 시총은 **+$314B(+24.9%)** 늘었다. 멀티플을 가격 예측기로 쓰는 건 불가능하고, **유입강도 대비 가격 반응(탄력성)의 변화**를 레짐 판정기로 쓰는 건 가능하다.

---

## 1. 이론 배경

BIS Working Paper 1104 *The Crypto Multiplier*(Cong·Prasad 외)가 이 개념을 화폐수량방정식으로 정식화했다.

- 멀티플 **k = Δ시가총액 / 순유입액**
- 이론상 **k > 1** — 유입 $1이 시총을 $1 이상 늘린다
- 결정변수: **투자 목적 보유 비중 vs 결제 유통 비중.** 투자로 잠긴 비율이 높을수록 k가 커진다
- 주요 코인은 결제 유통 비중이 매우 작아 k가 "sizeable"해진다

**중요**: BIS 논문은 k의 이론적 도출만 하고 **구체적 수치값은 제시하지 않는다.** k를 특정 숫자로 인용하는 자료는 대부분 논문 근거 없이 만든 것이다.

---

## 2. 실측 — 2026년 8월

### 2-1. 기본 데이터

| 항목 | 값 | 출처 |
|---|---|---|
| 7/31 종가 | $62,896.51 | YCharts / Fortune 교차검증 |
| 8/31 종가 | $78,553 | CoinGecko·YCharts·Investing 3중 일치 |
| 8월 수익률 | **+24.89%** | 계산 |
| 유통량 | 20,080,415 BTC | Coinbase / Newhedge |
| 시총 변화 | **+$314.4B** | 유통량 × 가격변화 |

> ⚠️ **정정**: 이전에 쓰던 7/31 앵커 $64,715.45는 **7/30 값**이다(또는 7/31 장초 값). 실제 7/31 종가는 $62,896.51. 이 때문에 8월 수익률은 +21.16%가 아니라 **+24.89%**다. 기존 문서에서 8월 수익률을 참조한 곳은 정정 필요.

### 2-2. 채널별 순유입 (8월 전체, US$B)

| 채널 | 순유입 | 신뢰도 | 비고 |
|---|---|---|---|
| BTC 현물 ETF | **+3.52** | 높음 | Farside 21거래일 전량 확인. TFTC "+$3.5B"와 일치 |
| 스테이블코인 순증 | **−6.00** | 중간 | DefiLlama 기준 7월말 $309.9B → 8월말 ~$303.9B. 8월말 값은 파생치 |
| DAT/기업 트레저리 | **+0.35** | 낮음~중간 | 자체 바텀업 집계. Strategy +1,275 net, Strive +3,136, Empery −100. Zhibao 2,380은 현물 인수(in-kind)라 제외 |
| 거래소 잔고 변화 | **−1.98** | 중간 | +28,000 BTC가 거래소로 **유입**(= 매도 대기 물량 증가) |
| **합계** | **−4.11** | — | |

### 2-3. 멀티플 계산 결과

| 정의 | 계산 | 결과 |
|---|---|---|
| k(ETF 단독) | +314.4 / +3.52 | **+89.2x** |
| k(채널 종합) | +314.4 / −4.11 | **−76.6x** ← 부호 역전 |

**두 값 모두 무의미하다.** 하나는 89배라는 물리적으로 설명 불가한 값이고, 하나는 부호가 반대다. 분모가 총수요를 담지 못하기 때문에 나오는 결과다.

### 2-4. 주간 분해 — 불안정성의 규모

| 주 | 구간 | 수익률 | Δ시총($B) | ETF($B) | k(나이브) | 유입강도 | 탄력성 |
|---|---|---|---|---|---|---|---|
| W1 | 8/02→8/09 | +2.13% | +27.1 | +0.854 | 31.8x | +0.235% | 9.0 |
| W2 | 8/09→8/16 | −3.10% | −40.4 | −0.388 | 104.1x | −0.105% | 29.6 |
| W3 | 8/16→8/23 | **+23.66%** | +298.6 | +1.918 | **155.7x** | +0.534% | 44.3 |
| W4 | 8/23→8/30 | −0.07% | −1.1 | +0.925 | **−1.2x** | +0.208% | **−0.3** |
| W5 | 8/30→9/04 | +2.59% | +40.4 | +0.987 | 41.0x | +0.223% | 11.7 |

- **k가 −1.2x ~ +155.7x 범위를 오간다.** 5주 만에 130배 스프레드. 이걸 상수로 쓰는 건 불가능
- 정의: **유입강도 = 주간 순유입 / 자유유통 시총**, **탄력성 = 주간 수익률(%) / 유입강도(%)**
- 자유유통 시총 = (20.08M − 14.37M illiquid) × 가격 = **5.71M BTC ≈ $359B**

---

## 3. 왜 상수가 아닌가 — 구조적 이유 4가지

### ① 측정 채널이 총수요를 span하지 않는다
8월 순유입 −$4.1B vs 시총 +$314B. 나머지는 오프쇼어 현물, OTC 블록, 그리고 **파생 주도 리프라이싱**이다. Farside가 잡는 건 미국 ETF 래퍼를 통과한 돈뿐이다.

### ② 델타중립 유입은 방향성 수요가 아니다
ETF 순유입 중 **캐시앤캐리(현물 매수 + CME 선물 매도)** 비중은 가격에 방향성 압력을 거의 주지 않고, 베이시스 축소 시 되돌림 물량이 된다. 같은 $1B이라도 캐리 비중이 높으면 k가 낮아진다. → CME OI와 베이시스로 추정해야 하며, `framework/perp-basis-regime-2026-09-01.md`와 함께 읽어야 한다.

### ③ 공급 탄력성이 시변한다
같은 $1도 자유유통이 얇으면 임팩트가 크다. 그런데 **8월엔 자유유통이 오히려 두꺼워졌다** — 거래소 잔고가 +28,000 BTC 늘고(6~7월 유출분의 84% 되돌림), 고래가 +60k BTC 모으는 동안 1~100 BTC 코호트가 −33k, 1 BTC 미만이 −14k를 분배했다. **8월 랠리는 공급 스퀴즈가 아니었다.** CoinDesk도 7/9자로 "거래소 준비금 감소가 예전만큼 강세 신호가 아니다"라고 같은 지적을 했다.

### ④ 역인과 — 유입이 가격을 따라간다
일별 25개 관측치(8/03~9/04) 상관계수:

| 관계 | 상관 | 해석 |
|---|---|---|
| 유입ₜ ↔ 수익률ₜ | **+0.784** | 강하지만 **동시성**. 인과 방향을 말해주지 않는다 |
| 유입ₜ → 수익률ₜ₊₁ | +0.234 | 약한 예측력 |
| 수익률ₜ₋₁ → 유입ₜ | **+0.312** | **유입이 가격을 추종** |

**추종성(0.312)이 예측력(0.234)보다 크다.** ETF 유입은 선행지표가 아니라 대체로 동행·후행 지표다. 0.784라는 숫자만 보고 "유입이 가격을 움직인다"고 읽으면 안 된다.

---

## 4. 그럼 무엇을 추적하는가 — 판정 프레임

절대 멀티플 대신 **유입강도 → 가격 반응(탄력성)**의 변화를 본다. 레벨이 아니라 **레짐 전환**이 신호다.

| 탄력성 | 유입 방향 | 판정 | 포지션 시사점 |
|---|---|---|---|
| **> 30** | + | 공급 경직 — 얇은 호가에 유입이 꽂힘 | 추세 가속 구간. 다만 같은 이유로 되돌림도 빠름. 추격보다 눌림 대기 |
| **10 ~ 30** | + | 정상 흡수 | 추세 유지. 포지션 유지 |
| **0 ~ 10** | + | 유입 대비 반응 둔화 | 상단 매물 출현. 신규 진입 보류 |
| **< 0** | + | 🔴 **탄력성 붕괴 — 유입되는데 안 오른다** | 분배 국면 의심. 최우선 경고. 익절/헤지 검토 |
| **> 30** | − | 유출 과민 반응 | 유동성 공백. 하방 갭 위험, 스탑 넓히지 말 것 |
| **0 ~ 10** | − | 유출 흡수 | 바닥 형성 시도. 분할 진입 후보 |

### 8월 적용 결과 (사후 검증)

| 주 | 탄력성 | 판정 | 실제 다음 주 |
|---|---|---|---|
| W1 | 9.0 | 정상 흡수 하단 | W2 −3.10% (약세) ✅ |
| W2 | 29.6 (유출) | 유동성 공백 | W3 +23.66% (급등) ❌ — 공백은 양방향 |
| W3 | 44.3 | 공급 경직·추세 가속 | W4 −0.07% (정지) — 되돌림 경고 ✅ |
| W4 | **−0.3** | 🔴 탄력성 붕괴 | W5 +2.59% (반등) ⚠️ **절반만 적중** |

**W4 경고의 성적**: 하락 전환은 틀렸지만 **추세 정지**는 맞았다. 8/27 고점 $80,268 이후 9/4까지 신고점을 못 갔다. 즉 이 신호는 **"추세 종료" 신호가 아니라 "가속 종료" 신호**로 해석해야 한다.

**W2의 오작동**은 프레임의 실제 약점이다. 유출 국면의 높은 탄력성은 방향을 알려주지 않고 변동성만 알려준다. **유출 구간에서는 탄력성 신호를 방향 판단에 쓰지 말 것.**

---

## 5. 추적 스펙 — 매주 기록할 항목

| # | 항목 | 소스 | 주기 |
|---|---|---|---|
| 1 | BTC 일별 종가 | CoinGecko / Investing | 일 |
| 2 | BTC 현물 ETF 순유입 | Farside `/btc/` | 일 |
| 3 | 스테이블코인 총 시총 | **DefiLlama 고정** (트래커 혼용 금지) | 주 |
| 4 | 거래소 스테이블 준비금 | CryptoQuant | 주 |
| 5 | BTC 거래소 잔고 | CryptoQuant 전체 거래소 기준 | 주 |
| 6 | DAT 매수/매도 | SEC 8-K, bitcointreasuries.net | 주 |
| 7 | CME 베이시스·OI | CoinGlass | 주 (델타중립 비중 추정용) |
| 8 | Illiquid supply | Glassnode | 월 (분모 갱신) |

**계산 순서**: 순유입 합계 → 자유유통 시총으로 나눠 유입강도 → 주간 수익률 ÷ 유입강도 = 탄력성 → 위 표로 판정.

**회귀 추정은 아직 하지 말 것.** 관측치 5주로는 β 추정이 무의미하다. **26주(6개월) 이상** 쌓인 뒤에 `Δln(P) = α + β·(순유입/자유유통시총) + controls` 형태로 돌리고, 그때 β가 비로소 "이 시장 구조에서의 멀티플" 추정치가 된다.

---

## 6. 한계 — 반드시 인지할 것

1. **표본 5주.** 통계적 유의성 없음. 판정 프레임의 임계값(30 / 10 / 0)은 8월 관측 분포에서 잡은 잠정치이며, 데이터가 쌓이면 재조정 대상이다.
2. **스테이블코인 8월말 값은 파생치.** DefiLlama 현재값에서 7일 변화를 역산했다. 공표된 수치가 아니다.
3. **트래커 레벨 차이.** DefiLlama $305.6B vs StablecoinBeat $303.0B (9/7 동일자, 차이 $2.6B). **한 차트에 섞지 말 것.**
4. **거래소 잔고 시리즈 충돌.** CryptoQuant 전체 거래소 ~2.72M BTC와 협의 시리즈 ~1.33M BTC는 2배 차이로 **화해 불가**. 레벨은 CryptoQuant, 주간 델타는 협의 시리즈 내부에서만 쓸 것.
5. **Illiquid supply 정의 혼재.** 17.7%(10년 미이동 = 소실) / 56.5%(활성 거래 외) / 72%(Glassnode illiquid)는 서로 다른 정의의 중첩 지표다. **평균 내지 말 것.** 본 문서는 Glassnode 72% 기준(14.37M BTC)을 분모에 썼다.
6. **스테이블코인 순증은 BTC향 수요가 아니다.** 스테이블로 BTC를 사면 스테이블은 소각되지 않고 손만 바뀐다. 순증은 "신규 법정화폐 → 크립토 부동자금" 유입을 재는 것이고, ETF 유입과 성격이 달라 단순 합산에 **이중계상/누락 위험**이 있다. 4장 프레임은 이 한계를 안고 있는 근사치다.
7. **DAT 채널은 사실상 닫혔다.** 8월 DAT 순증은 약 +4,310 BTC(현물 인수 제외)로 월간 신규 발행량 ~13,500 BTC의 **1/3 수준**. 2024년 반감기 이후 평균 2.8배 흡수하던 것과 대비된다. Strategy mNAV 0.81배, Twenty One 0.60배 — mNAV 1 미만은 주식 발행 플라이휠을 멈추게 하고, 우선주 배당은 계약상 의무로 남아 **DAT가 수요에서 공급으로 뒤집히는 비대칭**을 만든다. Strategy는 실제로 2026년 6,948 BTC를 매도했다.

---

## 7. 사이클 판정

8월 BTC는 측정 가능한 자금 유입 없이 +24.9% 올랐다. 스테이블코인은 −$6B 줄었고, 거래소 잔고는 +28k BTC 늘었으며, DAT는 사실상 중립이었다. 유일하게 플러스였던 채널은 ETF(+$3.5B)인데, 그것도 자유유통 시총의 1% 미만이다. 이건 **자금이 밀어올린 랠리가 아니라 얇아진 시장에서의 리프라이싱**에 가깝다. 8/17~21 한 주에 +23.7%가 몰린 집중도, 그리고 그 직전 주가 순유출이었다는 사실이 이를 뒷받침한다. 구조적으로 이런 랠리는 되돌림 속도도 같은 만큼 빠르다.

## 8. 포지션 시사점

멀티플을 진입 근거로 쓰지 말 것 — 8월이 보여준 대로 유입량과 가격 방향은 월 단위에서 부호조차 일치하지 않는다. 대신 **탄력성 붕괴(유입 지속 + 가격 무반응, W4 패턴)를 가속 종료 경고로만** 쓰는 게 현재 검증된 유일한 용법이다. 유출 구간의 탄력성은 방향 정보가 없으니 변동성 경고로만 읽는다. 그리고 지금 구조에서 진짜로 봐야 할 건 유입량보다 **DAT의 mNAV**다 — 1배 미만이 고착되면 우선주 배당 의무가 매도를 강제해 DAT가 수요 채널에서 공급 채널로 뒤집히고, 그때는 ETF 유입이 그 물량을 흡수해야 한다. Strategy가 $64K대에서 팔고 $80K대에서 되산 궤적은 이 채널이 가격에 순응적(procyclical)이라는 증거다.

---

## 출처

**가격·공급** — [YCharts BTC](https://ycharts.com/indicators/bitcoin_price) · [CoinGecko 히스토리](https://www.coingecko.com/en/coins/bitcoin/historical_data) · [Investing.com](https://www.investing.com/crypto/bitcoin/historical-data) · [Coinbase 유통량](https://www.coinbase.com/price/bitcoin) · [Newhedge](https://newhedge.io/bitcoin/circulating-supply)

**ETF 플로우** — [Farside BTC](https://farside.co.uk/btc/) · [TFTC ETF Flows](https://www.tftc.io/bitcoin-etf-flows) · [HedgeCo 9/1 유출](https://hedgeco.net/news/09/2026/spot-bitcoin-etfs-posted-a-236-5-million-net-outflow-on-september-1.html)

**스테이블코인** — [DefiLlama](https://defillama.com/stablecoins) · [StablecoinBeat](https://stablecoinbeat.com/tracker/) · [DailyCoin 8/19 거래소 준비금](https://dailycoin.com/stablecoin-liquidity-falls-as-reserves-concentrate-on-binance) · [CryptoBriefing 8/31](https://cryptobriefing.com/stablecoin-market-cap-987m-increase-dex-volumes/)

**온체인·공급** — [CoinDesk 7/9 거래소 준비금 해석](https://www.coindesk.com/markets/2026/07/09/bitcoin-s-dwindling-exchange-reserves-don-t-pack-the-same-bullish-punch-anymore) · [news.bitcoin.com 8/17 28k BTC 복귀](https://news.bitcoin.com/market-updates/bitcoin-supply-squeeze-unwinds-as-28000-btc-return-to-exchanges/) · [news.bitcoin.com 9/2 고래 축적](https://news.bitcoin.com/crypto-news/bitcoin-whale-accumulation-august-2026-cryptoquant/) · [KuCoin 8/16 소실 물량 ATH](https://www.kucoin.com/news/flash/bitcoin-s-lost-supply-hits-all-time-high-accounting-for-17-7-of-circulating-supply)

**DAT** — [SEC 8-K 8/24](https://www.sec.gov/Archives/edgar/data/1050446/000119312526361845/mstr-20260824.htm) · [CoinDesk 8/10 Strategy 매도](https://www.coindesk.com/markets/2026/08/10/strategy-sells-1-690-bitcoin-raises-usd653-million-from-mstr-shares) · [BitcoinTreasuries 8/31 매수 재개](https://bitcointreasuries.net/news/strategy-buys-4603-bitcoin-and-continues-strc-buybacks) · [The Block Strive 1,800](https://www.theblock.co/news/business/2026-08-31-strive-fifth-largest-public-bitcoin-treasury-1800-btc-buy-td-cowen-lifts-asst-price-target-413112) · [CryptoTimes $80B 소멸](https://www.cryptotimes.io/2026/08/27/80b-wiped-out-as-bitcoin-treasury-companies-face-model-breakdown/) · [BusinessWire BSTR SPAC 철회](https://www.businesswire.com/news/home/20260820107232/en/Bitcoin-Standard-Treasury-Company-BSTR-Terminates-Business-Combination-Team-Continues-Pursuing-Active-Bitcoin-Treasury-Management)

**이론** — [BIS WP1104 The Crypto Multiplier](https://www.bis.org/publ/work1104.pdf)

---
*정보 제공 목적이며 투자 권유가 아님.*
