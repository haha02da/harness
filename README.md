# Harness: Software Development Pipeline

Harness는 Gemini CLI 환경에서 **Planner → Developer → Reviewer**로 이어지는 3단계 파이프라인을 통해 소프트웨어 개발 작업을 체계적으로 자동화하는 도구입니다.

## 🚀 주요 기능

- **자동화된 개발 워크플로우**: 사용자 요구사항 분석부터 계획 수립, 코드 구현, 최종 리뷰까지 전 과정을 자동화합니다.
- **역할 기반 에이전트**:
    - **Planner**: 코드베이스를 탐색하여 기술 스택을 파악하고 실행 가능한 `plan.md`를 수립합니다.
    - **Developer**: 수립된 계획에 따라 코드를 작성하고 수정하며 구현 노트를 작성합니다.
    - **Reviewer**: 구현된 코드를 검토하고 버그를 발견하며, 크리티컬한 문제는 직접 수정합니다.
- **지속적인 컨텍스트 유지**: `_workspace/` 디렉토리를 통해 작업 이력을 관리하며, 부분 재실행 및 개선 요청을 효율적으로 처리합니다.

## 📁 프로젝트 구조

```text
.
├── .gemini/
│   ├── agents/          # 에이전트(Planner, Developer, Reviewer) 역할 정의
│   ├── skills/          # 개발 오케스트레이터 스킬 정의
│   └── settings.json    # Gemini CLI 설정
├── GEMINI.md            # 프로젝트 핵심 규칙 및 컨텍스트
└── README.md            # 프로젝트 설명 (현재 파일)
```

## 🛠 사용 방법

Gemini CLI에서 `dev-orchestrator` 스킬을 트리거하여 사용합니다.

- "로그인 API를 만들어줘"
- "버그 수정해줘"
- "기존 코드를 리팩토링해줘"

위와 같은 요청을 하면 하네스가 자동으로 파이프라인을 가동하여 작업을 수행합니다.

## 🔄 워크플로우

1. **Phase 1 (Planner)**: 요구사항 분석 및 `plan.md` 생성
2. **Phase 2 (Developer)**: 코드 구현 및 `implementation-notes.md` 작성
3. **Phase 3 (Reviewer)**: 코드 리뷰 및 `review.md` 작성 (필요 시 버그 수정)
4. **Phase 4 (Reporting)**: 최종 결과 및 변경 사항 보고
