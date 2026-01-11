# 📅 HOIN ENGINE 작업 일지 및 향후 계획 (2026-01-12)

## 1. ✅ 오늘 완료한 작업 (Current Status)
*   **Git 프로젝트 초기화**: 로컬 저장소 생성 및 GitHub 연동 완료.
*   **설계 문서화**:
    *   `Airtable_Structure.md`: 3개 주요 테이블(`metrics`, `metric_values`, `theme_learning`) 구조 정의.
    *   `Make_Structure.md`: 3개 주요 시나리오 폴더 및 데이터 흐름 설계.
    *   `DATA_COLLECTION_MASTER.md`: 초기 수집 대상 데이터 23종(Macro, FX, Crypto 등) 리스트 확정.
    *   `metric_id_rules.md`: 데이터 ID 생성 규칙(category.source.name) 확정.
*   **시스템 뼈대 구축 (UI 기준)**:
    *   Airtable: Base 및 Table 생성 가이드 완료.
    *   Make: 시나리오 생성, 주요 모듈(HTTP, Router, Airtable) 배치 완료.

## 2. ⚠️ 체크 필요 & 누락된 부분 (Missing/Check)
오늘 구조는 잡았지만, 실제 **'피(Data)'**가 돌기 위해 필요한 연결 고리들이 아직 비어 있습니다.

1.  **Airtable `metrics` 테이블 데이터 부재**
    *   `DATA_COLLECTION_MASTER.md`에 정의한 23개 지표를 Airtable의 `metrics` 테이블에 실제로 등록해야 합니다. (이게 없으면 데이터가 갈 곳이 없습니다.)
2.  **API Key 준비**
    *   **FRED API Key**: 거시경제 데이터 수집 필수.
    *   **OpenAI API Key**: 'Theme Learning' 및 분석용.
    *   **YouTube/Google API Key**: 영상/뉴스 수집용.
3.  **Make 상세 로직 미구현**
    *   HTTP 모듈이 껍데기만 있고, 실제로 FRED에 요청 주소(URL)를 넣는 작업이 안 되어 있습니다.
    *   가져온 데이터를 Airtable로 맵핑하는 '변수 연결' 작업이 필요합니다.

## 3. 🚀 내일의 실행 계획 (Next Steps)
**목표: "첫 번째 심장 박동" - 실제 데이터가 시스템을 타고 흐르게 하기**

### [오전] 기초 데이터 심기
1.  **Airtable `metrics` 등록**: 23개 초기 지표를 ID 규칙에 맞춰 Airtable에 수동/일괄 등록.
2.  **API Key 점검**: 사용자로부터 FRED, OpenAI 등 필수 키 확인 및 Make 연결.

### [오후] 데이터 파이프라인 연결 (Scenario 1)
3.  **FRED 연동 구현**: Make의 `Macro_Rates` 시나리오에서 실제 FRED 데이터를 호출.
4.  **자동 분류 로직(Router)**: 금리, 환율 등 카테고리별로 데이터가 제 자리를 찾아가도록 설정.
5.  **적재 테스트**: Make 버튼을 눌렀을 때, Airtable `metric_values`에 숫자가 꽂히는지 최종 확인.

---
**💡 최종 목표 리마인드**
> "이 엔진은 똑똑할 필요 없다. 대신 멈추지 않고 누적되어야 한다." & "무료 AI 사용량 제어 준수"
