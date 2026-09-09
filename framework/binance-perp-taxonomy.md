# 바이낸스 무기한 선물 분류 체계 (Taxonomy v2)

> 스냅샷: **2026-08-20 (UTC)** · 거래중 종목 **744개** · 24h 총 거래대금 **$122.9B**
> 산출물: `binance_perp_classification.xlsx` (7시트)

## 0. 핵심 발견 — TradFi 무기한 선물이 존재한다

바이낸스는 계약을 **`PERPETUAL`(크립토)** 와 **`TRADIFI_PERPETUAL`(전통금융)** 으로 나눠 제공한다.

| 계약군 | 종목수 | 24h 거래대금 | 비중 |
|---|---|---|---|
| 크립토 무기한 | 574 | $96.2B | 78.3% |
| **TradFi 무기한** | **170** | **$26.7B** | **21.7%** |

👉 **바이낸스 선물 거래대금의 5분의 1 이상이 이미 전통자산이다.** 이건 부수적 상품이 아니라 주력 라인이다.

### TradFi 자산 유형 (거래소 공식 `underlyingType`)
| 유형 | 종목수 | 내용 |
|---|---|---|
| `EQUITY` | 138 | 미국 주식 · ETF |
| `HK_EQUITY` | 12 | TENCENT, MEITUAN, POPMART, KUAISHOU, ZHIPU, MINIMAX … |
| `KR_EQUITY` | 8 | **SAMSUNG, SKHYNIX, NAVER, HYUNDAI, LGELECTRONICS, KODEX200, SAMSUNGEM, HANMI** |
| `COMMODITY` | 8 | XAU(금) XAG(은) XPT XPD CL BZ NATGAS COPPER |
| `PREMARKET` | 2 | **OPENAI, ANTHROPIC** (비상장 프리-IPO) |
| `CN_EQUITY` | 2 | CXMT, UNITREE |

---

## 1. 분류 구조 (4계층)

| 계층 | 출처 | 내용 |
|---|---|---|
| **L0 계약군** | 거래소 공식 | `PERPETUAL` / `TRADIFI_PERPETUAL` |
| **L1 자산유형** | 거래소 공식 | COIN / EQUITY / KR_EQUITY / HK_EQUITY / CN_EQUITY / COMMODITY / PREMARKET / INDEX |
| **L2 거래소 섹터태그** | 거래소 공식 (`underlyingSubType`) | TradFi 170 · DeFi 115 · Alpha 71 · Infrastructure 59 · AI 57 · Layer-1 53 · Meme 47 · Gaming 27 · Layer-2 21 · PoW 17 · NFT 11 · Metaverse 9 · Payment 7 · Storage 6 · RWA 4 … |
| **L3 자체 세부분류** | 본 프레임워크 | 아래 §2 · §3 |

> **원칙:** L0~L2는 거래소 공식 데이터를 그대로 신뢰하고, L3만 자체 판단. 자체 매핑이 없으면 L2 태그로 폴백 → **분류율 95%** (미분류 28/744).

---

## 2. TradFi 세부분류 (L3)

| 코드 | 한글 | 자산군 | 종목 | 24h 거래대금 |
|---|---|---|---|---|
| `TF-SEMI` | 반도체 · AI하드웨어 | 주식 | 36 | **$10.1B** |
| `TF-COMM-PM` | 귀금속(금·은·백금·팔라듐) | 원자재 | 4 | $4.13B |
| `TF-ETF-LEV` | 레버리지 · 인버스 ETF | 주식(ETF) | 6 | $3.59B |
| `TF-KR` | **한국 주식 · ETF** | 주식(한국) | 8 | **$2.93B** |
| `TF-EQ-OTHER` | 개별주 기타(확인필요) | 주식 | 17 | $2.70B |
| `TF-CRYPTOEQ` | 크립토 연관주 | 주식 | 8 | $0.97B |
| `TF-COMM-EN` | 에너지 원자재(원유·가스) | 원자재 | 3 | $0.95B |
| `TF-BIGTECH` | 빅테크 · 플랫폼 | 주식 | 18 | $0.45B |
| `TF-ETF-IDX` | 지수 ETF (SPY·QQQ·IWM) | 주식(ETF) | 3 | $0.26B |
| `TF-ETF-SECTOR` | 섹터 · 국가 ETF | 주식(ETF) | 9 | $0.18B |
| `TF-CN` | 중국 비상장 · 신흥 | 주식(중화권) | 2 | $0.13B |
| `TF-HK` | 홍콩 · 중국 주식 | 주식(중화권) | 12 | $0.11B |
| `TF-SOFTWARE` | 소프트웨어 · SaaS | 주식 | 12 | $0.05B |
| `TF-ENERGY` | 에너지 · 전력 · 원자력 | 주식 | 4 | $0.03B |
| `TF-INDUSTRIAL` | 산업재 · 우주항공 | 주식 | 6 | $0.03B |
| `TF-COMM-BASE` | 산업금속(구리) | 원자재 | 1 | $0.02B |
| `TF-PREIPO` | **프리-IPO (OPENAI, ANTHROPIC)** | 비상장 지분 | 2 | $0.012B |
| `TF-HEALTH` | 헬스케어 · 바이오 | 주식 | 3 | $0.011B |
| `TF-CONSUMER` | 소비재 · 리테일 | 주식 | 5 | $0.006B |
| `TF-FIN` | 금융 · 핀테크 | 주식 | 8 | $0.004B |
| **`TF-BOND`** | **채권(미국채) ETF — TMF, TBT** | **채권** | 2 | $0.002B |
| `TF-ETF-VOL` | 변동성(VIX) ETF — UVXY | 변동성 | 1 | $0.002B |

### TradFi 거래대금 TOP 10
`SNDK $5.94B` · `XAU $2.92B` · `SKHYNIX $2.55B` · `SOXL $1.76B` · `KORU $1.26B` · `SNXX $1.23B` · `XAG $1.19B` · `MU $1.18B` · `SPCX $1.18B` · `SKHY $1.17B`

> **관찰:** 반도체 · 메모리(SNDK, MU, SKHYNIX, SKHY)와 금이 압도적. **한국 반도체 노출이 단일 국가로는 최대.** 정작 AAPL·MSFT·GOOGL 같은 빅테크는 거래가 거의 없다 — 이 시장은 "24시간 레버리지로 반도체·금·한국주식을 치는 곳"에 가깝다.

### 채권 노출은 얼마 없다
직접 국채 선물은 없고, **TMF**(20년+ 미국채 3배 롱) / **TBT**(20년+ 미국채 2배 인버스) 두 개의 레버리지 ETF뿐. 거래대금도 $2.3M 수준으로 사실상 방치. **금리 뷰를 이 시장에서 표현하기는 어렵다.**

---

## 3. 크립토 세부분류 (L3)

| 대분류 | 종목 | 24h 거래대금 |
|---|---|---|
| 메이저 (BTC·ETH) | 13 | **$73.7B** (전체의 60%) |
| 레이어1 | 68 | $6.67B |
| 디파이 | 91 | $3.82B |
| 밈코인 | 59 | $3.04B |
| 결제 | 8 | $2.17B |
| 프라이버시 | 7 | $1.26B |
| 알파(신규·소형) | 66 | $0.99B |
| 인프라 | 54 | $0.89B |
| AI/에이전트 | 59 | $0.81B |
| 실물자산(RWA) | 11 | $0.48B |
| 게임/메타버스/NFT | 47 | $0.39B |
| 스테이블코인 | 6 | $0.29B |
| 레이어2 | 24 | $0.20B |
| DePIN | 14 | $0.13B |
| 스테이킹/리스테이킹 | 11 | $0.13B |
| 인터체인 | 8 | $0.12B |
| 기타/미분류 | 28 | $1.15B |

> **BTC·ETH가 크립토 거래대금의 76%**. 알트 전체를 합쳐도 TradFi 섹션($26.7B)보다 작다.

### 크립토 RWA / 토큰증권 (11종목, $0.48B)
여기서 반드시 구분할 것:

| | 설명 | 선물에 있나 |
|---|---|---|
| **토큰증권 자체** (AAPLx, OUSG, BUIDL 등) | 실제 주식·국채를 1:1 토큰화 | ❌ 없음 (규제상품) |
| **토큰화 *하는* 프로젝트 토큰** (ONDO, PLUME, POLYX, PENDLE, CFG, OM …) | 인프라·발행 플랫폼 | ✅ 이쪽이 매매 대상 |

RWA 세부코드: `RWA-EQ`(주식) `RWA-TSY`(국채·MMF) `RWA-BOND`(회사채) `RWA-CREDIT`(사모신용) `RWA-COMM`(금·원자재) `RWA-RE`(부동산) `RWA-INFRA`(발행 플랫폼)

**2026 시장규모 참고:** 토큰화 국채 ~$12.9B · 원자재 ~$7.4B · 사모신용 ~$5B(플랫폼 포함 $18~19B) · 회사채 ~$1.8B · 주식 ~$1B+ · 이더리움이 전체의 56%+

---

## 4. 교차 분류축 (모든 종목 병렬 부여)
| 축 | 값 |
|---|---|
| 유동성 티어 | `T1` ≥$1B · `T2` $200M~1B · `T3` $50~200M · `T4` <$50M |
| 변동성 등급 | `LOW` <3% · `MID` 3~7% · `HIGH` 7~15% · `EXTREME` ≥15% |
| 상장 연차 | `NEW` <1년 · `MID` 1~3년 · `LEGACY` 3년+ |

---

## 5. 미해결 / 다음 작업
- [ ] `TF-EQ-OTHER` 17종목 수동 확인 — 최근 상장이라 티커 식별 필요: **SNXX, SPCX, BBX, BOT, BSP, CBRS, FWDI, INTW, KSTR, LYTE, MUU, PENG, QNTX, SHAZ, STRC, STXX** (SNXX·SPCX는 거래대금 $1B+ 로 중요)
- [ ] 크립토 미분류 28종목 정리
- [ ] BTC 베타 산출 (일봉 히스토리 필요)
- [ ] **OKX · Bybit 동일 작업** → 3대 거래소 통합 분류표
- [ ] 주기적 신규 상장 추적

## 데이터 수집 방법 (중요)
바이낸스 API는 클라우드 환경에서 **451 지역차단**. 브라우저에서 아래 저장 후 첨부하는 방식으로 수집:
- `https://fapi.binance.com/fapi/v1/exchangeInfo`
- `https://fapi.binance.com/fapi/v1/ticker/24hr`

## 출처
- Binance Futures API (exchangeInfo / ticker24hr), 스냅샷 2026-08-20 UTC
- [MetaMask — RWA categories in 2026](https://metamask.io/news/types-of-tokenized-real-world-assets-rwa-categories)
- [Eco — Tokenized Equities 2026](https://eco.com/support/en/articles/15254023-tokenized-equities-2026-backed-dinari-robinhood)

---
*정보 제공 목적이며 투자 권유가 아님.*
