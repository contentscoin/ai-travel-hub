# AI TRAVEL 프로젝트 허브

회의에서 정리된 사업 흐름, 검토 상태, 미결 사항, 다음 단계와 근거를 모은 정적 사이트입니다.

- `index.html`: HTML 프로젝트 허브. 브라우저에서 직접 열 수 있습니다.
- `MEETING_REPORT_20260910.md`: 2026-09-10 후속 회의 결과 원문. 자율 운영 추가 회의 이전 이력이며, 추가 내용은 HTML에 반영했습니다.
- `.nojekyll`: GitHub Pages에서 정적 파일을 그대로 제공합니다.

2026-09-12 v2: 5단계 경영 운영, 14개 업무의 입력·담당·검수·인계·실패 대응과 미결을 반영했습니다.

- `OPERATING_PLAYBOOK_20260912.html` / `.md`: 전체 경영 운영 문서와 원본.
- `WORKFLOW_REGISTRY_20260912.html` / `.md`: Buzz 등록 14개 UUID·사용법·검증 범위.
- `workflows/W01.yaml` ~ `W14.yaml`: 서버에서 원문 일치를 확인한 업무 안내 정의. 일반 메시지 시작은 `filter: 'false'`로 차단하며 수동 실행 결과는 미검증입니다.
- `HUB_V1_20260910.html`: 이전 페이지 이력.

운영안은 `in_review`입니다. 체크리스트 등록과 상품 수집·마케팅 게시·유료 제작·실정산 자동화는 구분합니다. 등록된 카드로 업무가 자동 배정되거나 실행되지는 않습니다.

회의 결과는 수동 갱신합니다. 내용의 기준일과 설계·검토·실행 상태를 구분하고 이전 상태는 Git 이력으로 보존합니다.

페이지: https://contentscoin.github.io/ai-travel-hub/

저장소: https://github.com/contentscoin/ai-travel-hub

게시 설정: GitHub Pages의 브랜치 게시에서 `pages` 브랜치, 루트(`/`)를 사용합니다. 해당 브랜치에 변경 사항을 푸시하면 Pages가 다시 배포합니다.
