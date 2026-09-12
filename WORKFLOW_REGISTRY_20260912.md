# AI TRAVEL Buzz 업무 워크플로 등록 목록 — 2026-09-12

**14개 등록 완료, 서버 되읽기 14/14 일치. 실제 수동 실행은 아직 검증하지 않았습니다.**

등록 채널은 기존 프로젝트의 proj-ai-travel입니다. 기존 review-gate와 release-gate는 변경하지 않았습니다. 이 문서의 14개 정의는 각 업무를 시작할 때 필요한 체크리스트를 꺼내는 기능입니다. 업무 전반의 담당·인계·예외는 [운영 문서](OPERATING_PLAYBOOK_20260912.md)에 있습니다.

## 등록 목록

| ID | 업무 | Buzz workflow ID | 정의 |
|---|---|---|---|
| W01 | 전략·예산·주간 경영 | `b8dd15ee-5a74-4ff7-8991-d583273c810b` | [YAML](workflows/W01.yaml) |
| W02 | 수요·실험 기획 | `44d74cb5-75c7-4aa1-a153-1fd003741ed3` | [YAML](workflows/W02.yaml) |
| W03 | 파트너·상품·권리 원장 | `f881dd30-81e1-409f-bf73-3dac1388deb4` | [YAML](workflows/W03.yaml) |
| W04 | 마케팅·편집 계획 | `40c939c0-f885-4025-9ae1-6f76e04db661` | [YAML](workflows/W04.yaml) |
| W05 | 원고·비교 콘텐츠 | `e45f097c-8105-4db2-b7b1-7556b9736dbb` | [YAML](workflows/W05.yaml) |
| W06 | 디자인·랜딩 UX | `c1e1bc83-05bf-4614-9d32-3f009886c5b9` | [YAML](workflows/W06.yaml) |
| W07 | 영상·오디오 제작 | `11417107-b4fe-4479-914c-5fc29540e45a` | [YAML](workflows/W07.yaml) |
| W08 | 개발·수집·자동화 | `34f0648e-419a-4aac-9b93-342e1c93dc9b` | [YAML](workflows/W08.yaml) |
| W09 | 배포·변경·검수 | `b9d3505f-0fa1-4e0b-8406-2c6a78a556fb` | [YAML](workflows/W09.yaml) |
| W10 | 게시·갱신·회수 | `5e8ea02f-33a1-4ed0-a649-aac1a9a9f2a2` | [YAML](workflows/W10.yaml) |
| W11 | 성과·실험·개선 | `a386e8ab-aeb9-41c8-a028-a6c721ee37af` | [YAML](workflows/W11.yaml) |
| W12 | 정산·비용·수익 대조 | `9fa0c1b8-9a5e-47b4-b914-9da81ec4c077` | [YAML](workflows/W12.yaml) |
| W13 | 문의·장애·복구 | `ab454e3e-c143-4e5f-96b8-2a5b4e6dab18` | [YAML](workflows/W13.yaml) |
| W14 | 팀·권한·문서·업무 인계 | `0b547496-8791-45f3-bf21-c612d67fba7a` | [YAML](workflows/W14.yaml) |

## 시작 방법

프로젝트 채널에서 agentmaker에게 업무 ID와 실제 요청 범위를 알려 주세요. 예: “W12 정산 대조 체크리스트를 열어줘.” 이것은 실제 이체·정산 확정·비용 집행 지시와 구분합니다.

워크플로 소유자 agentmaker의 CLI 실행 예시:

```powershell
buzz workflows trigger --workflow 9fa0c1b8-9a5e-47b4-b914-9da81ec4c077
```

로컬 소스 조사상 CLI 수동 실행은 워크플로 소유자만 가능합니다. 사용자 본인의 CLI로 agentmaker 소유 워크플로를 실행할 수 있다고 확인한 것은 아닙니다. 수동 시작에는 답글 스레드 인자가 없어 **같은 프로젝트 채널 최상위에 안내 카드 한 장**이 게시됩니다. 일반 결과 보고는 원래 회의 스레드에 남깁니다.

## 실제 기능과 범위

- 각 정의는 `enabled: true`, `on: message_posted`, `filter: 'false'`입니다. 일반 메시지로 시작되지 않도록 설정했습니다. `manual`이라는 trigger 종류는 현재 확인한 소스에 없습니다.
- 액션은 `send_message` 하나입니다. 안내문에 입력·담당 후보·산출물·검수·인계·예외처리를 담습니다.
- 웹훅·시간 예약·외부 API·실제 수집·게시·렌더·결제 액션은 정의에 없습니다.
- 카드가 나왔다고 업무가 배정되거나 수행된 것은 아닙니다. 실제 작업은 이슈 생성·서명 배정·담당 수신·실행 증거·별도 검수를 연결해야 합니다.
- 업무 완료를 기다리는 다단계 실행기, 도구 자동화, 예산 집행 권한은 별도 구현 사항입니다.
- 정의 변경은 새로 중복 생성하지 않고 해당 UUID를 `workflows update`로 갱신합니다.

## 확인 근거

2026-09-12 `buzz workflows create`의 accepted=true 및 `buzz workflows list` 되읽기로 UUID·소유자·UTF-8 YAML을 원본과 비교했습니다. 14개 모두 일치했습니다. 일반 메시지 자동 시작 차단은 정의와 소스의 필터 분기에서 확인했으며, 운영 서버에서 의도적 메시지를 넣는 실행 시험은 수행하지 않았습니다. `workflows runs`의 빈 배열을 실행 성공으로 해석하지 않았습니다.

CLI/엔진 조사: 로컬 `REPOS/buzz-contentscoin` HEAD `bc4970725c1b44c2604ca18ec96ae69bc7194a47`의 `crates/buzz-workflow/src/schema.rs`, `lib.rs`, `executor.rs`, `crates/buzz-cli/src/commands/workflows.rs`, `crates/buzz-relay/src/handlers/command_executor.rs`. 이 소스 버전과 운영 서버 버전의 일치를 검증한 것은 아닙니다.
