# 거래소 API 접근성 매트릭스 (클라우드 세션 기준)

> 최종 테스트: 2026-09-01. 이 프로젝트의 데이터 수집 경로를 결정하는 운영 문서.
> 기존 `coins_00-INDEX.md` 운영 섹션의 "바이낸스 API 451 지역차단" 메모를 이 표로 대체·확장.

## 1. 실측 결과

| 소스 | 엔드포인트 | 클라우드 직접 | 브라우저 경유 | 판정 |
|---|---|---|---|---|
| Binance 선물 | `fapi.binance.com/fapi/v1/*` | **451** | ✅ **200** | 🟡 브라우저 전용 |
| Binance 현물 | `api.binance.com/api/v3/*` | **451** | ✅ 가능 | 🟡 브라우저 전용 |
| Bybit | `api.bybit.com/v5/*` | **403** | ✅ 가능 | 🟡 브라우저 전용 |
| **OKX** | `www.okx.com/api/v5/*` | **200** | — | 🟢 전면 |
| **Hyperliquid** | `api.hyperliquid.xyz/info` (POST) | **200** | — | 🟢 전면 |
| **Deribit** | `www.deribit.com/api/v2/public/*` | **200** | — | 🟢 전면 |
| **Coinbase** | `api.coinbase.com` · `api.exchange.coinbase.com` | **200** | — | 🟢 전면 |
| CoinGlass open-api | `open-api.coinglass.com` | 200 | — | 🟡 **API 키 필요** |
| CoinGlass Liquidation Map | 웹 | — | 🔒 로그인 게이트 | 미수집 |

**핵심**: Binance는 브라우저로 뚫린다. `fapi.binance.com/futures/data/*` 계열(openInterestHist,
topLongShortPositionRatio, takerlongshortRatio)까지 JSON 그대로 읽힌다. 다만 **브라우저는 데스크톱
연결이 필요**하므로 무인 스케줄 작업에는 쓸 수 없다 — 자동화는 클라우드 직접 소스만으로 구성할 것.

## 2. 경로 선택 규칙

| 필요 데이터 | 경로 | 자동화 가능 |
|---|---|---|
| OKX OI·펀딩·L/S·테이커볼륨 (현재+시계열) | 파이썬 직접 | ✅ |
| Hyperliquid OI·펀딩·프리미엄·오더북·계정 포지션 | 파이썬 직접 | ✅ |
| Coinbase 프리미엄 (미국 현물 수요 판정) | 파이썬 직접 | ✅ |
| Deribit 옵션·퍼프 | 파이썬 직접 | ✅ |
| Binance OI·상위트레이더 L/S 시계열 | 브라우저 | ❌ 수동 |
| Bybit | 브라우저 | ❌ 수동 |
| CME OI, 전 거래소 집계, 청산 히트맵 | CoinGlass 웹 + 브라우저 | ❌ 수동 |

## 3. 교차 검증 (2026-09-01 동일 시점)
| 항목 | API 직접 | CoinGlass 웹 | 일치 |
|---|---|---|---|
| Hyperliquid BTC OI | 37,572.01 BTC | 37.57K BTC | ✅ |
| OKX BTC-USDT-SWAP OI | 27,308 BTC | 34.89K BTC (전 계약 합산) | ⚠ 단일 계약 vs 합산 차이 |

→ 웹 스크린샷 판독은 신뢰 가능. 단 CoinGlass의 거래소 OI는 **해당 거래소의 전 BTC 계약 합산**이므로
단일 심볼 API 값과 직접 비교하면 안 된다.

## 4. Binance 유용 엔드포인트 (브라우저 전용)
```
/fapi/v1/openInterest?symbol=BTCUSDT
/futures/data/openInterestHist?symbol=BTCUSDT&period=1d&limit=30
/futures/data/topLongShortPositionRatio?symbol=BTCUSDT&period=1d&limit=30   ← 큰손 포지션 편향
/futures/data/globalLongShortAccountRatio?symbol=BTCUSDT&period=1d&limit=30
/futures/data/takerlongshortRatio?symbol=BTCUSDT&period=1d&limit=30
/fapi/v1/fundingRate?symbol=BTCUSDT&limit=100
```

## 5. API가 웹 스크린샷보다 나은 점
1. **시계열** — OI/펀딩 추이로 "OI 늘면서 오르는지(레버리지 주도) 안 늘면서 오르는지(현물 주도)" 판정. 스냅샷으로는 불가.
2. **자동화** — 스케줄 작업 편입 (→ `automation/btc-desk-build.py`).
3. **계산** — 프리미엄·베이시스·가중평균 직접 산출.
4. **Hyperliquid 심층** — `clearinghouseState`로 개별 대형 계정의 포지션·레버리지·청산가 조회 → CoinGlass 청산지도를 원본으로 재현·검증 가능. (미실행, 대기 중)

## 6. 연결된 자동화
- `automation/btc-desk-build.py` + `automation/btc-desk-template.html`
- 스케줄: 매일 **09:00 / 21:00 KST** (cron `0 0,12 * * *` UTC), 클라우드 전용 소스만 사용
- 산출물: BTC 파생 포지셔닝 데스크 아티팩트 (고정 URL, 매회 덮어쓰기)

---
*정보 제공 목적이며 투자 권유가 아님.*
