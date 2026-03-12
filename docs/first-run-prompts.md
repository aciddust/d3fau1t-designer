# First Run Prompts

이 문서는 이 저장소에서 바로 실행할 수 있는 첫 번째 명령 세트를 제공합니다.

## 1. Structure and Planning

```md
/web-product-pipeline
프로젝트 타입은 website 이다.
목표는 운영 중인 마켓플레이스에 등록할 AI 웹 제작 플러그인의 소개 사이트를 만드는 것이다.
주 타겟은 AI 워크플로우를 도입하려는 팀 리드와 제품 담당자다.
핵심 성공 이벤트는 플러그인 설치 요청이다.
보조 성공 이벤트는 데모 요청과 파일럿 논의 시작이다.
브랜드 톤은 실무 중심, 빠른 실행, 과장 없는 설명이다.
필수 페이지는 홈, 기능 설명, 워크플로우 설명, 사용 예시, FAQ 이다.
선호 스택은 Next.js 이고 현재 코드베이스는 없다.
기존 입력 자료로 NOTE.md, README.md, docs/marketplace-positioning.md 를 참고해도 된다.
```

## 2. Figma MCP Handoff

```md
/web-design-handoff
방금 만든 구조를 기준으로 Figma MCP용 handoff spec을 만들어줘.
데스크톱과 모바일 기준으로 프레임 목록, 섹션 구조, 토큰, 컴포넌트, 상태값을 정리해줘.
시각 톤은 화려한 마케팅보다 신뢰감 있는 운영 도구에 가깝게 잡아줘.
CTA 영역과 워크플로우 설명 구간은 특히 구현 가능성이 높게 구체화해줘.
```

## 3. Frontend Plan

```md
/web-build
위에서 만든 product structure와 figma spec을 기준으로 Next.js 구현 계획을 만들어줘.
현재 저장소에는 앱 코드가 없으니 실제 파일 생성 대신 스캐폴드 계획, 폴더 구조, 우선 구현 순서, 검증 체크리스트를 docs/frontend-plan.md 로 정리해줘.
```

## 4. Homepage-specific Variant

```md
/homepage-pipeline
이 플러그인을 소개하는 단일 랜딩 페이지를 만들고 싶다.
목표는 플러그인 설치 요청 전환이다.
타겟은 AI 워크플로우 도입을 검토하는 팀 리드다.
핵심 메시지는 브리프에서 구조, 디자인, 구현 계획까지 하나의 Claude 워크플로우로 연결된다는 점이다.
```