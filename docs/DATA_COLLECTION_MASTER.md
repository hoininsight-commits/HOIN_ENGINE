# HOIN ENGINE – Data Collection Master List (Official)

## 목적
- 가능한 한 많은 신뢰 가능한 데이터를 수집하기 위한 기준 문서
- Make / Airtable / 분석 로직의 상위 기준
- 모든 데이터 수집 논의는 이 문서를 기준으로 한다

## 운영 원칙
- 모든 데이터 수집은 누적 방식
- 중복 데이터라도 다른 지표 산출 가능 시 유지
- 동일 데이터 + 로직 파생 지표는 별도 표시
- 수집 여부는 Make 시나리오 기준으로만 변경
- 상태 변경 시 Git commit 필수

## 상태 정의
- READY: 수집 가능, 아직 Make 미구현
- COLLECTING: Make에서 정상 수집 중
- PAUSED: 기술적 이슈로 중단
- BLOCKED: 무료/신뢰 문제로 제외


---

## 데이터 수집 리스트

| 카테고리 | 수집 데이터 | 주요 수집처 | 수집 방식 | 무료 | 환각 리스크 | 수집 여부 | 비고 |
|--------|------------|-------------|-----------|------|-------------|-----------|------|
| Macro | 미국 기준금리 | FRED | API | O | 매우 낮음 | READY | |
| Macro | 한국 기준금리 | 한국은행 | CSV | O | 매우 낮음 | READY | |
| Macro | 미국 국채 2Y | FRED | API | O | 매우 낮음 | READY | |
| Macro | 미국 국채 10Y | FRED | API | O | 매우 낮음 | READY | |
| Macro | 금리 스프레드 (10Y-2Y) | FRED | API | O | 매우 낮음 | READY | [파생] |
| Macro | CPI | FRED | API | O | 매우 낮음 | READY | |
| Macro | PPI | FRED | API | O | 매우 낮음 | READY | |
| Macro | 실업률 | FRED | API | O | 매우 낮음 | READY | |
| Macro | M2 통화량 | FRED | API | O | 매우 낮음 | READY | |

| FX | USD/KRW | FRED | API | O | 매우 낮음 | READY | |
| FX | DXY | FRED | API | O | 매우 낮음 | READY | |
| FX | USD/JPY | FRED | API | O | 매우 낮음 | READY | |

| Equity | S&P500 지수 | Stooq | CSV | O | 낮음 | READY | |
| Equity | NASDAQ 지수 | Stooq | CSV | O | 낮음 | READY | |
| Equity | KOSPI 지수 | KRX | CSV | O | 낮음 | READY | |
| Equity | KOSDAQ 지수 | KRX | CSV | O | 낮음 | READY | |
| Equity | VIX | CBOE / FRED | API | O | 매우 낮음 | READY | |

| Credit | 회사채 스프레드 (IG) | FRED | API | O | 매우 낮음 | READY | |
| Credit | 하이일드 스프레드 | FRED | API | O | 매우 낮음 | READY | |

| Commodity | 금 가격 | FRED (LBMA) | API | O | 매우 낮음 | READY | |
| Commodity | 은 가격 | FRED | API | O | 매우 낮음 | READY | |
| Commodity | WTI 원유 | FRED | API | O | 매우 낮음 | READY | |
| Commodity | 구리 가격 | FRED | API | O | 낮음 | READY | |

| Crypto | 비트코인 가격 | CoinGecko | API | O | 낮음 | READY | |
| Crypto | 이더리움 가격 | CoinGecko | API | O | 낮음 | READY | |
| Crypto | 전체 시총 | CoinMarketCap | API | O | 낮음 | READY | |

| RealEstate | 주택가격지수 | 한국부동산원 | CSV | O | 낮음 | READY | |
| RealEstate | 미분양 주택수 | 국토교통부 | CSV | O | 낮음 | READY | |

| Sentiment | 소비자심리지수 | 한국은행 | CSV | O | 매우 낮음 | READY | |
| Sentiment | 제조업 PMI | S&P Global (공개치) | Manual/CSV | O | 중간 | READY | |

| Media | 경제사냥꾼 업로드 | YouTube | RSS | O | 낮음 | READY | |
| Media | 주요 경제 뉴스 | Google News | RSS | O | 중간 | READY | |

