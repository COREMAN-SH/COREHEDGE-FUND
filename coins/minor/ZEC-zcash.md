# ZEC (Zcash) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
비트코인에서 포크된 "선택적 프라이버시(optional privacy)" 코인. zk-SNARK 영지식증명으로 발신자·수신자·금액을 완전히 가리는 "쉴디드(shielded)" 거래를 제공하는 프라이버시 전문 체인.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **zk-SNARK (Halo2 / Orchard)** | 신뢰 설정(trusted setup) 부담 없이 거래 내역을 완전히 숨기는 영지식증명 기술 |
| **쉴디드 풀 (Sapling → Orchard → Ironwood)** | 실제 프라이버시가 발생하는 핵심 구조. 최근 Ironwood 업그레이드로 확장, 규모가 $10억 돌파 |
| **Equihash 작업증명(PoW)** | 비트코인과 유사한 채굴 기반 합의(스테이킹 아님) |
| **Zashi 지갑 + NEAR Intents** | 모바일 지갑에서 타 체인 자산을 프라이빗하게 스왑하는 크로스체인 연동 |
| **Project Tachyon (NU7 예정)** | 완전 검증 라이트클라이언트 + 대규모 확장성 + 양자내성 준비를 목표로 한 차세대 프로토콜 |

## 3. 토크노믹스
- 최대 발행량 **2,100만 ZEC**(비트코인과 동일 설계), 반감기도 약 4년 주기(1차 2020.11 → 2차 2024.11)
- 현재 블록 보상 **1.5625 ZEC/블록**, 다음(3차) 반감기는 **2028년경** 예상
- 유통량 약 **1,690만 ZEC**(전체의 ~80%)
- 🎯 **쉴디드 풀 비중 30%+로 사상 최고치** — 프라이버시 코인 중 실사용 지표가 가장 뚜렷하게 개선된 사례로, 감시 강화 시대의 실질 수요를 나타내는 핵심 온체인 지표
- ⚠️ 구조적 약점: 투명 주소(t-addr)와 쉴디드 주소(z-addr)가 공존하는 이원 구조라, 기본값이 프라이버시가 아니면 실효성이 떨어짐 — "쉴디드 기본값(shielded-by-default)"으로의 전환이 로드맵의 핵심 과제
- ⚠️ 규제 리스크: EU가 **2027년 7월까지 프라이버시 코인 자체를 금지**하는 자금세탁방지규정(AMLR) 도입을 추진 중 — 거래소 상장폐지·유동성 축소 압력의 근원

## 4. 로드맵 · 관전 포인트
1. **양자복구 지갑(Quantum-Recoverable Wallet) 출시** ← 가장 중요
   - 2026년 상반기 출시, 2027년까지 완전 양자내성(post-quantum) 전환 목표의 1단계
2. **Project Tachyon / NU7 업그레이드**
   - 완전 검증 라이트클라이언트 도입 + Ironwood 쉴디드 풀 확장으로 프라이버시 트랜잭션 처리량 확대
3. **Zashi + NEAR Intents 크로스체인 프라이빗 스왑**
   - 타 체인 자산을 ZEC로 프라이빗 스왑하는 기능의 실사용 전환이 관건
   - ⚠️ ZachXBT 등이 NEAR Intents 연동 과정에서 추적 가능성(트레이서빌리티) 결함을 지적 — 완전한 프라이버시 보장인지 추가 검증 필요
4. **Grayscale 등 현물 ETF 신청 진행** 🎯
   - Grayscale ZEC 현물 ETF 'ZCSH'가 2026-08-25 NYSE Arca에 실제 상장 완료, 이후 자산 성장 가속화(섹션 5 참조)

## 5. 시장 현황
- 가격 / 시총: 2026-09-04 전후 ZEC $1,178.24(24h +16.81%)까지 급등 — 9/4 장중 약 $1,050 신사상최고가 경신, 90일 기준 +144% 상승. 8/25 기록한 8년 만의 최고가 $888을 재차 큰 폭으로 경신.
- 최근 촉매: Grayscale 현물 ETF 'ZCSH'가 8/25 상장 이후 8일 만인 9/3 자산규모(AUM) $414.7M 달성 — 프라이버시 코인 ETF 중 이례적으로 빠른 성장세. 9/4 숏스퀴즈 발생으로 24시간 내 공매도 포지션 약 $34.5M 청산. 9/5 Bitwise CIO Matt Hougan이 ZEC를 향후 10년 필수 자산으로 재차 지목하며 "AI 감시 증가로 금융 프라이버시 수요가 늘고 있다"고 언급. 8/29 발표된 Zakura 암호화 도구모음 출시로 비공개 거래 생성 시간이 3초→200ms로 단축.

## 6. 실무 알림 사항
- 단기 과열 국면(90일 +144%, 숏스퀴즈 동반) — 변동성 확대에 따른 청산 리스크에 유의할 것.
- Grayscale ZCSH ETF 자산 성장 속도가 매우 빠른 만큼(상장 8일 만에 $414.7M), 추가 프라이버시 코인 ETF 상장 러시 가능성과 거래소별 취급 정책 변화를 계속 모니터링.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | 감시 강화 시대 "진짜 프라이버시" 수요 구조적 증가, 쉴디드 풀 비중 사상 최고치, Cypherpunk Technologies 등 기관형 매수 주체 등장, 현물 ETF(ZCSH) 상장 이후 빠른 자산 성장 |
| **약세 논리** | EU 프라이버시 코인 금지 추진 등 되돌리기 어려운 구조적 규제 리스크, 거래소 상장폐지 압박의 반복적 전례, 쉴디드 채택이 아직 전체 공급의 소수에 불과, 단기 급등에 따른 되돌림 리스크 |
| **트리거** | 추가 거래소·기관 ETF 자금 유입 규모, EU AMLR 최종 입법 내용, NU7/Tachyon 실제 출시 일정, 주요 거래소 상장폐지 뉴스 |

## 출처
- [Zcash (ZEC) - CoinGecko](https://www.coingecko.com/en/coins/zcash)
- [What are the economics of Zcash? - Z.Cash](https://z.cash/learn/what-are-the-economics-of-zcash/)
- [Building the Zcash Machine: Tachyon and Quantum Readiness - CoinDesk](https://www.coindesk.com/research/building-the-zcash-machine-tachyon-and-quantum-readiness)
- [Why 30% of Zcash supply is now in the shielded pool - crypto.news](https://crypto.news/why-30-of-zcash-supply-is-now-in-the-shielded-pool/)
- [Grayscale Investments Advances Plans For Spot Zcash (ZEC) ETF - Crowdfund Insider](https://www.crowdfundinsider.com/2026/08/300059-grayscale-investments-advances-plans-for-spot-zcash-zec-etf-through-updated-sec-filing/)
- [EU to Ban Privacy Coins, Anonymous Accounts and Cap Cash by July 2027 - Yahoo Finance](https://finance.yahoo.com/markets/crypto/articles/eu-ban-privacy-coins-anonymous-120215953.html)
- [ZachXBT flags privacy flaw in Zashi Wallet's NEAR Intents integration - Cryptopolitan](https://www.cryptopolitan.com/zachxbt-flags-privacy-flaw-in-zashi-wallets-near-intents-integration/)
- [Zcash Targeting Post-Quantum Crypto Milestone by 2027 - Decrypt](https://decrypt.co/367250/zcash-targeting-post-quantum-crypto-milestone-by-2027)
- [Yahoo Finance — Zcash Hits Highest Price in Nearly a Decade, Crushing Short Bets](https://finance.yahoo.com/markets/crypto/articles/zcash-hits-highest-price-nearly-162446704.html)
- [CoinMarketCap — Zcash 최신 업데이트](https://coinmarketcap.com/cmc-ai/zcash/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
