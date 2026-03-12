# Claude Code Web Workflow

이 워크스페이스는 이제 홈페이지 전용이 아니라 웹페이지, 웹사이트, 웹서비스 제작 전반을 다루는 Claude Code용 프로젝트 커맨드 세트를 포함합니다. 홈페이지 리뉴얼은 이 범용 워크플로우의 한 가지 적용 사례로 취급합니다.

## Core Commands

### /web-product-pipeline
- 입력: 프로젝트 브리프, 타겟 유저, KPI, 콘텐츠, 브랜드 제약, 기술 제약
- 출력: 구조 정의, Figma handoff spec, 구현 스펙, 검증 계획
- 권장 사용 시점: 프로젝트 초반, 범위와 산출물 구조를 한 번에 정리할 때

### /web-design-handoff
- 입력: 브리프 또는 IA, 브랜드 가이드, 레퍼런스, 디바이스 우선순위
- 출력: Figma MCP 실행용 프레임, 토큰, 컴포넌트, 상태 정의
- 권장 사용 시점: 구조가 정리된 뒤 디자인 산출물을 빠르게 만들 때

### /web-build
- 입력: IA 또는 디자인 스펙, 구현 제약, 목표 스택
- 출력: 기존 앱이 있으면 구현, 없으면 구현 계획 문서
- 권장 사용 시점: 디자인 스펙을 코드 작업으로 전환할 때

## Specialized Example Commands

### /homepage-pipeline
- 범용 파이프라인의 랜딩 페이지, 홈페이지 특화 버전

### /homepage-figma-handoff
- 홈페이지 구조에 맞춘 Figma MCP 지시서 버전

### /homepage-build
- 홈페이지 구현 범위에 맞춘 빌드 버전

## 권장 운영 순서

1. .claude/templates/web-project-brief-template.md 를 채워서 브리프를 만든다.
2. /web-product-pipeline 에 브리프를 넣어 구조와 빌드 스펙을 만든다.
3. /web-design-handoff 로 Figma MCP 실행용 디자인 지시서를 만든다.
4. /web-build 로 실제 코드 작업 또는 스캐폴드 계획을 만든다.
5. 프리뷰 배포 후 QA, 이벤트, 실험 가설을 검증한다.

## Example Input

```md
/web-product-pipeline
프로젝트 타입은 webservice 이다.
사업 목표는 마켓플레이스 운영자가 신규 플러그인을 탐색하고 도입하도록 만드는 것이다.
주 타겟은 AI 워크플로우 도입을 검토하는 팀 리드다.
핵심 성공 이벤트는 플러그인 설치 또는 도입 문의다.
브랜드 톤은 실무 중심, 빠른 실행, 과장 없는 데모 지향이다.
우선 스택은 Next.js를 선호한다.
```

## 산출물 원칙

- 문서는 바로 다음 단계 에이전트가 사용할 수 있을 정도로 구체적이어야 한다.
- 모호한 항목은 숨기지 말고 assumption으로 드러내야 한다.
- 디자인 산출물은 시각적 수사보다 구현 가능성이 우선이다.
- 코드 단계에서는 기존 코드베이스가 없으면 무리하게 구현하지 않고 계획으로 멈춘다.