# WLD (Worldcoin) 리서치 노트

> 최종 업데이트: 2026-09-07

## 1. 한 줄 정의
**"인간 증명(Proof of Human/Personhood)" 인프라** — Sam Altman이 공동창업한 World Network가 홍채 스캔 하드웨어(Orb)로 생성한 고유 신원(World ID)을 기반으로, AI 시대에 "사람 vs 봇/에이전트"를 구분해주는 디지털 신원 네트워크의 유틸리티 토큰.

## 2. 핵심 기술 스택
| 구성요소 | 역할 |
|---|---|
| **Orb(오브)** | 홍채를 스캔해 고유 생체 해시를 생성하는 전용 하드웨어 기기. 보안 다자간연산(MPC)으로 12,800비트 암호화 코드로 변환 후 원본 이미지는 즉시 삭제한다고 설명(8/21 공개) |
| **World ID** | Orb 인증으로 발급되는 영지식(ZK) 기반 신원 증명. 한 사람이 여러 개의 디지털 신원을 만들 수 없도록(시빌 저항) 설계, 실제 신원 정보 노출 없이 "고유한 사람임"만 증명 |
| **World Chain** | OP 스택 기반 이더리움 L2(옵티미즘 슈퍼체인 계열). World ID 인증 사용자에게 우선순위·가스비 혜택 등을 부여해 봇 스팸을 억제하는 것이 특징 |
| **World App** | 지갑 + World ID 인증 + 미니앱 생태계를 통합한 슈퍼앱, WLD 보관 및 결제 인터페이스 |
| **AgentKit / x402 연동** | 2026년 3월 Coinbase 주도 x402(에이전트 결제 표준)와 연계해 "AI 에이전트 뒤에 실제 사람이 있음"을 증명하는 기업용 API 제공 |

## 3. WLD 토큰의 역할과 구조적 특징
- **최대 발행량 100억 WLD(고정)**, 유통량 약 36.3억 개(약 36%), 시총 약 13.5억 달러, FDV 약 37.2억 달러 (2026-09-01 CoinGecko 기준) — 시총/FDV 비율 0.36으로 4대 코인 중 잠긴 물량 비중이 가장 큼 ⚠️
- 배분 구조: **커뮤니티 75%** / 팀·투자자(TFH)·소규모 준비금 25%
- 언락 방식: **클리프 없는 매일 선형 언락**. 2026-07-24부로 일일 언락 속도가 **43% 감소**(약 510만 → 약 290만 WLD/일) — 커뮤니티 물량은 320만→160만(-50%), 팀·투자자 물량은 190만→130만(-32%)으로 각각 축소 🎯 (공급 과잉 완화 신호로 해석 가능, 섹션 6에서도 계속 유효한 요인으로 언급)
- 토큰 효용: World ID로 인증된 사용자에게 UBI 성격의 정기 지급(Grants), World App 내 결제·수수료 매개, 향후 거버넌스 참여 예정
- ⚠️ **세계 각국의 규제 리스크**: 브라질·독일·태국·필리핀·홍콩·인도네시아 등에서 전면/사실상 금지, 스페인·포르투갈·프랑스·인도·케냐 등에서 조사 및 일시 중단 이력 — 홍채 등 생체정보 수집에 대한 각국 개인정보 당국의 민감한 반응이 반복적 규제 리스크로 작용

## 4. 2026 로드맵 (핵심 관전 포인트)
1. **"AI 에이전트 시대의 인간 증명" 피벗** ← 가장 중요
   - 2026년 3월 Coinbase의 x402 결제 표준과 연동한 AgentKit 출시, 4월 "새로운 World ID"로 Tinder·Zoom·Docusign 등과 파트너십 발표 — 딥페이크·봇 사기 방지 수요를 겨냥해 단순 UBI 코인에서 "AI 시대 필수 인프라"로 내러티브 확장
2. **미국 중심 확장 전략**
   - 유럽 대비 생체정보 규제가 상대적으로 느슨한 미국 시장에 집중, 6개 도시 약 7,000대 오브 운영(2025년 기준) 지속 확대
3. **언락 속도 완화** 🎯
   - 2026-07-24 일일 언락 43% 감소 조치의 시장 반응 지속 여부 — 공급 압력 완화가 가격에 실제로 반영되는지가 관전 포인트
4. **글로벌 규제 대응**
   - 금지국 재개 협상(케냐 사례처럼 조사 후 재개) 여부, 신규 금지국 추가 여부

## 5. 시장 현황
- 가격 / 시총: 2026년 9월 초 기준 WLD $0.4178(24h +3.85%). 8/19 +12.38% 반등 이후 거래량이 +39.71% 급증하며 매수심리 일부 회복.
- 최근 촉매: 9/4 CFTC 규제 플랫폼 Kalshi가 WLD 무기한선물 계약을 상장 — 미국 트레이더 대상 규제된 파생상품 접근성이 확대되며 기관 수요 유입 통로로 해석. 9/5 일부 애널리스트가 내부자 매도 증가와 시장 심리 악화를 근거로 WLD를 모니터링 대상 알트코인으로 지정.

## 6. 실무 알림 사항
- Kalshi 무기한선물 상장은 미국 규제 파생상품 시장 진입의 첫 사례 — 관련 거래량·미결제약정 추이를 신규 지표로 추적할 것.
- 내부자 매도 증가 경고가 나온 만큼, 온체인 대규모 이체(팀/재단 지갑) 여부를 주기적으로 확인 권장. 언락 속도 43% 감축(7/24 시행) 효과는 계속 유효.

## 7. 투자 관점 요약
| | 내용 |
|---|---|
| **강세 논리** | AI 에이전트 확산과 함께 "사람임을 증명"하는 수요가 구조적으로 커질 잠재력, Tinder·Zoom·Docusign 등 대형 플랫폼과의 파트너십으로 실사용처 확대, 2026-07 언락 속도 43% 감소로 공급 과잉 우려 일부 완화, Kalshi 규제 파생상품 상장으로 기관 접근성 신규 확보 |
| **약세 논리** | 시총/FDV 0.36으로 4개 코인 중 잠긴 물량 비율이 가장 높아 장기 공급 부담 지속. 브라질·독일 등 다수 국가의 금지·조사로 글로벌 스케일 확장에 구조적 제약. 생체정보 수집 방식 자체에 대한 프라이버시 논란이 상시 잠재 리스크. 최근 내부자 매도 증가 경고 |
| **트리거** | ① Tinder/Zoom 등 신규 파트너십의 실사용 지표(연동 사용자 수) ② 추가 국가의 금지/허용 여부 변화 ③ 언락 감소 이후 실제 유통량 증가율과 가격 반응 |

## 출처
- [Worldcoin (WLD) — CoinGecko](https://www.coingecko.com/en/coins/worldcoin)
- [Tokenomics Milestone: WLD unlock rate to decrease by 43% in July — World.org](https://world.org/blog/foundational-topics/tokenomics-milestone-wld-unlock-rate-to-decrease-by-43-in-july)
- [The Circulating Supply of Worldcoin (WLD): An Explainer — World.org](https://world.org/blog/foundational-topics/the-circulating-supply-of-worldcoin-wld-an-explainer)
- [US tech embraces Sam Altman's World iris-scan ID banned in places — Rest of World](https://restofworld.org/2026/sam-altman-worldcoin-zoom-tinder-partnerships/)
- [World launches agentkit with Coinbase-backed x402 to verify human identity behind AI agents — CoinDesk](https://www.coindesk.com/tech/2026/03/17/sam-altman-s-world-teams-up-with-coinbase-to-prove-there-is-a-real-person-behind-every-ai-transaction)
- [The New World ID: Proof of Human for the AI Era Scales Across the Digital Platforms People and Businesses Use Every Day — BusinessWire](https://www.businesswire.com/news/home/20260417530721/en/The-New-World-ID-Proof-of-Human-for-the-AI-Era-Scales-Across-the-Digital-Platforms-People-and-Businesses-Use-Every-Day)
- [What Is World Chain? Worldcoin's L2 Complete Guide 2026 — DEXTools](https://www.dextools.io/tutorials/what-is-world-chain-worldcoin-l2-guide-2026)
- [CoinMarketCap — Worldcoin 최신 업데이트](https://coinmarketcap.com/cmc-ai/worldcoin-org/latest-updates/)

---
*정보 제공 목적이며 투자 권유가 아님.*
