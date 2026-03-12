# AI Web Production — Claude Plugin

**웹페이지 · 웹사이트 · 웹서비스** 제작을 위한 Claude Code 플러그인입니다.

브리프를 입력하면 정보 구조 설계, Figma MCP handoff 명세, 프론트엔드 구현 계획, 검증 루프까지 하나의 파이프라인으로 연결됩니다. 기획 → 디자인 → 개발로 이어지는 순차 전달 구조를 Claude 명령 세트로 대체합니다.

---

## 설치

이 저장소를 사용하려는 프로젝트에 클론하거나 서브모듈로 추가합니다.

```bash
# 새 프로젝트에 클론
git clone https://github.com/d3fau1t-design/ai-web-production my-project
cd my-project

# 또는 기존 프로젝트에 서브모듈로 추가
git submodule add https://github.com/d3fau1t-design/ai-web-production .claude-plugin
```

설치가 끝나면 Claude Code에서 이 저장소를 열기만 하면 플러그인이 자동으로 인식됩니다.  
별도의 빌드나 설정 과정은 없습니다.

---

## 동작 방식

이 플러그인은 Claude Code의 **프로젝트 커맨드** 시스템 위에서 작동합니다.

```
Claude Code 채팅에서 /명령어 를 입력
       ↓
.claude/commands/ 안의 해당 명령 파일 실행
       ↓
.claude-plugin/ 안의 agents, skills, hooks 가 조합되어 응답 생성
       ↓
산출물이 docs/ 에 파일로 저장
```

각 구성 요소의 역할은 아래와 같습니다.

| 구성 요소 | 위치 | 역할 |
|---|---|---|
| Commands | `.claude/commands/` | 직접 입력하는 슬래시 명령 |
| Agents | `.claude-plugin/agents/` | 복수 단계를 이어서 처리하는 오케스트레이터 |
| Skills | `.claude-plugin/skills/` | 각 단계의 구체적인 실행 로직 |
| Hooks | `.claude-plugin/hooks/` | 단계 완료 시 자동 실행되는 검증·알림 |
| Proposals | `.claude-plugin/proposals/` | 상황에 맞는 다음 명령 제안 |
| Templates | `.claude-plugin/templates/` | 브리프 입력 양식 |
| Defaults | `.claude-plugin/defaults/` | 기본 스택, 출력 경로, 동작 플래그 |

---

## 빠른 시작

### 1단계 — 브리프 작성

`.claude-plugin/templates/web-project-brief.md` 를 열어 내용을 채웁니다.

최소한 아래 네 항목만 있으면 파이프라인을 시작할 수 있습니다.

```
프로젝트 타입: webpage / website / webservice
목표: 무엇을 만들고 왜 만드는지
타겟 유저: 누구를 위한 것인지
성공 이벤트: 문의, 가입, 설치, 구매 등
```

### 2단계 — 전체 파이프라인 실행

Claude Code 채팅에서 `/web-product-pipeline` 을 입력하고 브리프 내용을 붙여 넣습니다.

```
/web-product-pipeline
프로젝트 타입은 website 이다.
목표는 AI 웹 제작 플러그인의 소개 사이트를 만드는 것이다.
주 타겟은 AI 워크플로우 도입을 검토하는 팀 리드다.
핵심 성공 이벤트는 플러그인 설치 요청이다.
브랜드 톤은 실무 중심, 과장 없는 방식이다.
선호 스택은 Next.js 이다.
```

Claude가 아래 산출물을 순서대로 만들어 `docs/` 에 저장합니다.

| 파일 | 내용 |
|---|---|
| `docs/project-brief.md` | 정리된 브리프 |
| `docs/product-structure.md` | 페이지 구조, IA, 유저 플로우 |
| `docs/figma-spec.md` | Figma MCP 실행용 디자인 명세 |
| `docs/build-spec.md` | 프론트엔드 구현 스펙 |
| `docs/frontend-plan.md` | 스캐폴드 계획 (코드베이스 없을 때) |
| `docs/validation-plan.md` | QA, 애널리틱스, 실험 체크리스트 |

### 3단계 — 디자인 명세만 별도로 실행할 때

구조가 이미 있고 Figma MCP 실행용 명세만 필요할 때 사용합니다.

```
/web-design-handoff
docs/product-structure.md 를 기준으로 Figma MCP용 스펙을 만들어줘.
데스크톱과 모바일 프레임, 디자인 토큰, 컴포넌트 목록, 카피 플레이스홀더,
MCP 실행 체크리스트가 모두 포함되어야 한다.
브랜드 톤은 미니멀하고 실무적이다.
```

결과물은 `docs/figma-spec.md` 에 저장됩니다.

### 4단계 — 구현 계획 또는 실제 구현

```
/web-build
docs/figma-spec.md 와 docs/product-structure.md 를 기준으로
Next.js 구현 계획을 만들어줘.
현재 저장소에는 앱 코드가 없으니 스캐폴드 계획, 폴더 구조,
파일 생성 순서, 검증 체크리스트를 docs/frontend-plan.md 에 정리해줘.
```

> 이미 앱 코드가 있는 저장소라면 Claude가 기존 구조를 읽고 직접 파일을 수정합니다.

---

## 명령어 목록

### 범용 명령 (Core)

| 명령 | 설명 | 권장 입력 |
|---|---|---|
| `/web-product-pipeline` | 브리프 → 구조 → 디자인 → 구현 계획 → 검증 전체 실행 | 브리프 전문 |
| `/web-design-handoff` | IA 또는 브리프 → Figma MCP 실행용 디자인 명세 | 구조 문서 또는 브리프 |
| `/web-build` | 디자인 스펙 → 구현 계획 또는 실제 코드 작업 | 스펙 문서, 스택, 제약 |

### 홈페이지 특화 명령 (Specialized)

범위가 단순한 랜딩 페이지나 홈페이지에 특화된 버전입니다.

| 명령 | 설명 |
|---|---|
| `/homepage-pipeline` | 홈페이지 단위로 최적화된 전체 파이프라인 |
| `/homepage-figma-handoff` | 홈페이지 구조에 맞춘 Figma MCP 명세 |
| `/homepage-build` | 홈페이지 범위의 프론트엔드 구현 계획 |

---

## 플러그인 구조

```
.claude-plugin/
├── plugin.json                            ← 플러그인 매니페스트
├── commands/                              ← Claude Code 슬래시 명령 파일
│   ├── web-product-pipeline.md
│   ├── web-design-handoff.md
│   ├── web-build.md
│   ├── homepage-pipeline.md
│   ├── homepage-figma-handoff.md
│   └── homepage-build.md
├── agents/
│   ├── web-production-agent.agent.md      ← 전체 파이프라인 오케스트레이터
│   └── design-handoff-agent.agent.md     ← Figma 명세 전담 에이전트
├── hooks/
│   ├── on-brief-received.json             ← 파이프라인 실행 전 브리프 검증
│   ├── on-design-handoff-complete.json   ← 디자인 명세 완료 후 알림·제안
│   └── on-build-complete.json            ← 구현 계획 완료 후 검증 체크리스트
├── proposals/
│   ├── new-web-project.md                 ← 브리프 감지 시 파이프라인 제안
│   ├── handoff-after-structure.md        ← 구조 완성 후 디자인 단계 제안
│   └── build-after-design.md             ← 디자인 완성 후 빌드 단계 제안
├── skills/
│   ├── brief-intake/SKILL.md              ← 날것의 브리프를 구조화
│   ├── ia-generator/SKILL.md             ← IA, 사이트맵, 유저 플로우 생성
│   ├── figma-spec-writer/SKILL.md        ← 디자인 토큰·컴포넌트·MCP 체크리스트
│   └── frontend-planner/SKILL.md        ← 구현 계획 또는 스캐폴드 생성
├── templates/
│   ├── web-project-brief.md               ← 범용 프로젝트 브리프 양식
│   └── homepage-brief.md                 ← 홈페이지 전용 브리프 양식
└── defaults/
    └── defaults.json                      ← 기본 스택, 출력 경로, 동작 플래그
```

---

## 자동 동작 (Hooks & Proposals)

명령을 실행하면 파이프라인의 각 단계가 완료될 때 자동으로 아래 동작이 실행됩니다.

**브리프를 받았을 때 (`on-brief-received`)**
파이프라인 실행 전에 브리프에 프로젝트 타입, 비즈니스 목표, 타겟 유저, 성공 이벤트가 있는지 검증합니다. 누락된 항목이 있으면 경고를 표시하고 계속 진행합니다.

**디자인 명세가 완성됐을 때 (`on-design-handoff-complete`)**
`docs/figma-spec.md` 저장을 확인하고, 미결 디자인 결정 사항을 리스트로 제시한 뒤 `/web-build` 실행을 제안합니다.

**구현 계획이 완성됐을 때 (`on-build-complete`)**
`docs/frontend-plan.md` 또는 `docs/build-spec.md` 저장을 확인하고, 프리뷰 배포 전 검증 체크리스트를 제시합니다.

**Proposals**
Claude가 대화 맥락에서 신규 브리프를 감지하거나, 이전 단계 산출물이 완성되면 자동으로 다음 단계 명령 실행을 제안합니다.

---

## 누구에게 유용한가

- 기획, 디자인, 개발을 순차로 전달하는 병목 구조를 깨고 싶은 팀
- 랜딩 페이지나 홈페이지 리뉴얼을 소수 인원으로 빠르게 처리해야 하는 그로스팀
- Figma MCP와 Claude Code를 연결해 실무 워크플로우를 지속 운영하고 싶은 팀
- 이 플러그인을 마켓플레이스에 올려 다른 팀에 전파하고 싶은 운영팀

---

## 기본값

`defaults/defaults.json` 에 정의된 기본값입니다. 브리프에서 별도로 지정하면 덮어씌워집니다.

| 항목 | 기본값 |
|---|---|
| 선호 스택 | Next.js |
| CSS 전략 | Tailwind CSS |
| 패키지 매니저 | pnpm |
| 배포 대상 | Vercel |
| 코드베이스 없을 때 자동 스캐폴드 | 비활성 (명시 요청 필요) |
| 기존 문서 덮어쓰기 | 비활성 (업데이트) |

---

## 라이선스

MIT
