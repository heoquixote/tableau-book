## 학습 목표

- Tableau MCP의 개념과 목적을 설명할 수 있습니다.
- Tableau MCP와 Tableau Next MCP의 차이를 구분할 수 있습니다.
- Tableau 기능을 외부 AI 에이전트에 연결할 때 MCP가 왜 중요한지 이해할 수 있습니다.

## 목차

1. Tableau MCP란?
2. Tableau MCP가 하는 일
3. Tableau Next MCP와의 차이
4. 실무에서 왜 중요한가?

## 1. Tableau MCP란?

Tableau MCP는 Tableau 기능을 외부 AI 에이전트나 애플리케이션과 연결하기 위한 Model Context Protocol 기반 인터페이스입니다.  
공식 AI 소개 페이지와 Tableau AI 관련 블로그에서는 Tableau MCP를 통해 커스텀 AI 에이전트가 Tableau의 데이터 질문 응답, 거버넌스된 분석, 메타데이터 해석 보조 기능을 활용할 수 있다고 설명합니다.

즉, Tableau MCP는 “Tableau 안에서 AI를 쓰는 기능”이라기보다, `외부 AI가 Tableau를 안전하게 활용하게 만드는 연결 계층`에 가깝습니다.

## 2. Tableau MCP가 하는 일

공식 설명 기준으로 Tableau MCP는 다음 방향에 초점이 있습니다.

- 게시된 데이터 원본 기반 데이터 질문 응답
- 거버넌스된 분석 수행
- Pulse 지표 활용
- Tableau 메타데이터 기반 해석 보강

2025.2 기능 소개에서는 Tableau MCP가 OAuth를 지원하고, Tableau Pulse 도구를 MCP 호환 에이전트에 연결할 수 있다고 안내합니다.

즉, MCP는 단순 API 호출보다 `에이전트가 이해하기 쉬운 형태로 Tableau 기능을 노출`하는 역할을 합니다.

## 3. Tableau Next MCP와의 차이

공식 자료에서는 `Tableau MCP`와 `Tableau Next MCP`를 구분해 설명합니다.

| 구분 | Tableau MCP | Tableau Next MCP |
| --- | --- | --- |
| 중심 대상 | Tableau Cloud / Server 기반 기능 연결 | Tableau Next 기반 에이전트 분석 연결 |
| 초점 | 데이터 질문, Pulse, 메타데이터, 결정적 분석 | 더 복잡한 대화형 분석과 에이전트형 분석 |
| 활용 방향 | 기존 Tableau 자산을 AI 에이전트에 연결 | Tableau Next 분석 경험을 AI 에이전트에 연결 |

실무에서는 “현재 운영 중인 Tableau Cloud/Server 자산을 AI와 연결하고 싶은가”, 아니면 “Tableau Next 기반의 더 확장된 agentic analytics를 다루고 싶은가”로 구분해서 보는 편이 이해하기 쉽습니다.

## 4. 실무에서 왜 중요한가?

MCP가 중요한 이유는 AI 에이전트가 데이터에 접근할 때 가장 큰 문제가 다음 두 가지이기 때문입니다.

- 신뢰할 수 있는 데이터에 어떻게 연결할 것인가
- 권한과 거버넌스를 어떻게 유지할 것인가

Tableau MCP는 이 지점에서 의미가 있습니다.

- 이미 조직 안에서 관리되는 Tableau 자산을 재활용할 수 있고
- Pulse, 메타데이터, 게시된 데이터 원본 같은 자산을 AI에 연결할 수 있으며
- 보안과 접근 제어를 더 체계적으로 유지할 수 있습니다

즉, MCP는 “AI가 데이터를 잘 말하게 하는 기능”이 아니라, `조직의 신뢰된 분석 자산을 AI 워크플로에 연결하는 운영 계층`이라고 이해하시면 됩니다.
