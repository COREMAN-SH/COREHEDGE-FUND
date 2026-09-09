# BTC (Bitcoin) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
정부·기관의 개입 없이 검증 가능한 방식으로 **디지털 희소성**을 만들어낸 최초의 자산 — 최대 발행량이 코드로 고정된 **탈중앙 P2P 전자화폐이자 디지털 금**.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **PoW (SHA-256 작업증명)** | 채굴자 간 경쟁적 해시 연산으로 블록 생성 — 위변조에 막대한 에너지 비용을 요구해 보안 확보 |
| **UTXO 모델** | 계좌 잔액이 아닌 "미사용 거래 출력값" 단위로 소유권 추적 — 병렬 검증에 유리 |
| **나카모토 합의** | 가장 긴(작업량 많은) 체인을 진실로 채택하는 규칙. 최종성은 확률적(6컨펌 관행) |
| **Lightning Network** | 오프체인 결제 채널 기반 2계층 — 소액·고빈도 결제를 온체인 밖에서 처리 |
| **Taproot/Segwit** | 서명 데이터 분리·슈노어 서명 등으로 용량 절감 및 스마트컨트랙트(covenant) 확장 기반 마련 |

## 3. 토크노믹스
- 최대 발행량 **2,100만 BTC**로 프로토콜에 하드코딩, 그 이상은 영원히 발행 불가
- 2026년 6월 기준 유통량 약 **2,004.7만 BTC**(발행 예정량의 약 95.5% 채굴 완료), 남은 채굴량 약 **95.3만 BTC**
- 블록 보상은 약 21만 블록(4년)마다 반감 — 현재 보상 **3.125 BTC/블록**(2024년 4월 4차 반감기 이후), 다음 반감기는 **약 2028년 초(블록 1,050,000)** 예정, 보상 1.5625 BTC로 축소
- 연간 신규 발행량은 약 16.4만 BTC 수준까지 감소 — 마지막 사토시는 이론상 **2140년경** 채굴 완료 예정
- ⚠️ **보안 예산(Security Budget) 논쟁**: 반감기가 반복될수록 채굴자 보상은 수수료 의존도가 커지는데, 현재 수수료는 채굴자 매출의 1% 미만 수준 — 장기적으로 수수료 시장이 성숙하지 못하면 네트워크 보안(해시레이트) 유지 유인이 약화될 수 있다는 구조적 우려가 존재
- 토큰 유틸리티는 가치저장·결제 수단에 집중 — 스마트컨트랙트 기능은 의도적으로 제한적(covenant 확장 논의 진행 중)

## 4. 2026 로드맵 (핵심 관전 포인트)
1. **커버넌트(Covenant) 소프트포크 논쟁** ← 가장 중요
   - OP_CTV, OP_CAT, LNHANCE, BitVM2 등 다수 제안 경쟁 중 — 비트코인 L1에 제한적 스마트컨트랙트 기능(비신뢰 볼트, 배치 처리 등)을 부여하는 것이 목표
   - BIP-446/448(OP_TEMPLATEHASH) 등 구체적 BIP 논의 진행, 2026년 8월 커뮤니티 내 "포크" 관련 논쟁(BIP-110, 양자내성 등) 격화
2. **양자 컴퓨팅 대비 논의** — 장기적으로 ECDSA 서명 체계의 양자내성 전환 필요성 제기, 구체적 실행 시점은 미정
3. **Lightning Network 및 L2 생태계 확장** — 결제 활용성 확대, 채널 용량·라우팅 개선
4. **현물 ETF·기관 채택 심화** — 국부펀드·연기금 등 신규 기관 자금 유입 경로 확대 지속

## 5. 시장 현황
- 가격 / 시총: 2026-09-03 기준 BTC $77,934.11(전일대비 +1.64%, 1개월 전 $63,201.02 대비 +23.31%). 전고점 $126,198.07(2025-10-06) 대비 약 -38% 하회. 9/3~9/5 사이 단기 이평선이 장기 이평선을 상향 돌파하는 "골든크로스" 형성이 임박했다는 분석 다수 제기(Fortune, CoinCentral, Blockonomi).
- 최근 촉매: 스팟 BTC ETF가 최근 3주간 누적 약 $3.8B 순유입을 기록 — 2026년 들어 가장 강한 3주 연속 유입 구간으로 평가(KuCoin, LCX, Parameter, Blockonomi, 9/5). 다만 CoinDesk는 9/1 "Rektember" 분석에서 최근 10년 중 6번의 9월이 하락 마감(평균 -6.53%)했다며 금리인상 리스크발 되돌림 가능성도 함께 경고 — 기관 자금 유입과 계절적 약세 신호가 공존하는 국면.

## 6. 실무 알림 사항
- ETF 자금 흐름이 3주 연속 순유입 국면 — 유입 속도 둔화·역전 여부를 주간 단위로 계속 체크할 것.
- 골든크로스 형성 시점 전후로 변동성이 확대될 수 있어 레버리지 포지션 리스크 관리 권고. 이번 주(8/31~9/7) 지갑/브릿지/거버넌스 관련 특이 리스크 이벤트는 확인되지 않음.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | 2,100만 개 하드캡의 절대적 희소성, 최장 트랙레코드의 탈중앙 네트워크, 현물 ETF를 통한 기관·국부펀드 자금 유입 통로 확보, "디지털 금" 내러티브의 매크로 헤지 수요 |
| **약세 논리** | 반감기 이후 장기 보안 예산(수수료 시장) 불확실성, 스마트컨트랙트 기능 제한으로 인한 생태계 확장성 한계, 2025년 10월 고점($126,080) 대비 큰 폭 조정을 겪은 이력, 규제·거시환경 변화에 민감 |
| **트리거** | 커버넌트 소프트포크(OP_CAT류)의 실제 활성화 여부, 현물 ETF 순유출입 추이, 연준 금리·유동성 정책 변화 |

## 출처
- [Coinlaw — Bitcoin 공급량 통계 2026](https://coinlaw.io/how-many-bitcoins-are-there-statistics/)
- [BlockEden — 비트코인 커버넌트 르네상스(OP_CTV/CAT/BitVM2)](https://blockeden.xyz/blog/2026/04/21/bitcoin-covenant-renaissance-op-ctv-lnhance-cat-bitvm2/)
- [Bitcoin Index — BIP-446 & BIP-448 OP_TEMPLATEHASH](https://bitcoinindex.net/blog/bip-446-bip-448-op-templatehash-brings-advanced-covenant-cap/)
- [AMINA Group — 2026년 8월 비트코인 포크 논쟁(BIP-110·양자시계)](https://aminagroup.com/research/bitcoin-fork-august-2026-bip-110-ecash-covenants-and-the-quantum-clock/)
- [CryptoSlate — 비트코인 수수료가 채굴자 매출의 0.5%에 불과, 2,100만 캡 논쟁 재점화](https://cryptoslate.com/peter-todd-reopens-bitcoins-21m-cap-debate-because-transaction-fees-make-up-just-0-5-of-miner-revenue/)
- [Fortune — 2026년 9월 3일 비트코인 가격](https://fortune.com/article/price-of-bitcoin-09-03-2026/)
- [KuCoin — Bitcoin ETF 3주 연속 $3.8B 순유입, 2026년 기록](https://www.kucoin.com/news/flash/bitcoin-etf-sees-3-8b-net-inflows-over-three-weeks-in-2026-record)
- [CoinDesk — 비트코인, 통계적으로 약한 9월("Rektember") 진입](https://www.coindesk.com/markets/2026/09/01/bitcoin-enters-rektember-as-rate-hike-risks-threaten-its-august-rally)

---
*정보 제공 목적이며 투자 권유가 아님.*
