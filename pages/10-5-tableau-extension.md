## 학습 목표

- Tableau Extension의 개념과 Dashboard Extension, Viz Extension의 차이를 이해할 수 있습니다.
- `.trex` 파일이 실제로 어떤 역할을 하는지 설명할 수 있습니다.
- MCP, 외부 API, LLM을 Tableau 대시보드 안으로 연결하는 기본 구조를 이해할 수 있습니다.
- Tableau Extension을 실무에 적용할 때 보안, 권한, 배포 관점에서 무엇을 주의해야 하는지 설명할 수 있습니다.

## 목차

1. Tableau Extension이란?
2. `.trex` 파일의 역할
3. MCP와 Extension의 역할 차이
4. AI와 결합하면 무엇을 만들 수 있을까?
5. Tableau Extension 개발의 기본 흐름
6. 실무에서 주의할 점

## 1. Tableau Extension이란?

Tableau Extension은 `Tableau 대시보드 안에 외부 웹 애플리케이션을 올려서`, 대시보드와 상호작용하게 만드는 기능입니다.

즉, Tableau가 원래 제공하는 필터, 차트, 툴팁만 쓰는 것이 아니라:

- 별도의 AI 채팅 패널
- 외부 뉴스 검색 패널
- 보고서 생성 버튼
- 추천 차트 가이드 화면

같은 기능을 `대시보드 내부 UI`로 직접 붙일 수 있습니다.

한 줄로 정리하면:

> Tableau가 데이터를 보여주는 캔버스라면, Extension은 그 위에 내가 만든 앱을 얹는 방식입니다.

### 1-1. Dashboard Extension과 Viz Extension

Extension에는 크게 두 종류가 있습니다.

- Dashboard Extension: 대시보드의 객체(Object)로 들어가는 확장
- Viz Extension: 워크시트 안에서 새로운 시각화 타입처럼 동작하는 확장

이 장에서 다루는 것은 주로 `Dashboard Extension`입니다.

왜냐하면 우리가 만들고 싶은 많은 AI 기능은:

- 대시보드 옆에 설명 패널을 띄우거나
- 선택한 마크를 읽어서 외부 서비스를 호출하거나
- 버튼을 눌러 문서를 생성하거나
- 대화형 보조 화면을 붙이는 형태

이기 때문입니다.

즉, 실무에서 "AI를 태블로 안에 붙인다"라고 할 때 가장 먼저 떠올릴 대상은 대개 Dashboard Extension입니다.

## 2. `.trex` 파일의 역할

많은 분들이 `.trex`를 "익스텐션 파일" 정도로 이해하시는데, 조금 더 정확히 말하면 `Extension 등록용 Manifest 파일`입니다.

실무적으로 중요한 포인트는 다음과 같습니다.

- `.trex` 파일이 실제 UI를 담고 있는 것은 아닙니다.
- 실제 화면은 HTML/JavaScript로 만든 웹 애플리케이션입니다.
- `.trex`는 Tableau에게 `어느 URL의 웹 앱을 어떤 이름과 권한으로 불러올지` 알려주는 등록 파일입니다.

즉, 기존에 이미 만들어 둔 웹 화면이 있다면 그 화면을 새로 다시 만드는 것이 아니라, `그 웹 화면을 가리키는 .trex 파일을 추가`해서 Tableau 안으로 불러오는 구조에 가깝습니다.

그래서 "기존 웹 화면을 Trex로 감싸서 태블로 안에 넣는다"는 표현은 사용자 관점에서는 맞지만, 원리로 보면 `Trex가 웹 앱을 감싸는 포장지`라기보다 `Tableau용 연결 설정서`에 더 가깝습니다.

### 2-1. `.trex` 예시

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest manifest-version="0.1" xmlns="http://www.tableau.com/xml/extension_manifest">
  <dashboard-extension id="com.example.ai.insight" extension-version="1.0.0">
    <default-locale>en_US</default-locale>
    <name resource-id="name"/>
    <description>AI Insight Panel</description>
    <author
      name="Your Name"
      email="you@example.com"
      organization="My Company"
      website="https://example.com"/>
    <min-api-version>1.0</min-api-version>
    <source-location>
      <url>https://example.com/tableau-extension/index.html</url>
    </source-location>
    <icon>BASE64_ENCODED_ICON</icon>
    <permissions>
      <permission>full data</permission>
    </permissions>
    <context-menu>
      <configure-context-menu-item />
    </context-menu>
  </dashboard-extension>
  <resources>
    <resource id="name">
      <text locale="en_US">AI Insight Panel</text>
    </resource>
  </resources>
</manifest>
```

이 예시에서 핵심은 아래입니다.

- `id`: 익스텐션을 고유하게 식별하는 값
- `source-location`: 실제 웹 앱이 떠 있는 URL
- `min-api-version`: 필요한 Extensions API 최소 버전
- `permissions`: 원본 데이터 접근이 필요할 때 선언
- `context-menu`: Configure 메뉴를 붙일 때 사용

실무적으로 특히 많이 헷갈리는 부분은 `source-location`입니다.

- 개발 중에는 `http://localhost`를 사용할 수 있습니다.
- 운영 환경에서는 보통 `HTTPS`로 서비스해야 합니다.

즉, `.trex`만 잘 만든다고 끝나는 것이 아니라, `뒤에서 실제로 서비스되는 웹 앱과 URL 운영`까지 함께 설계해야 합니다.

## 3. MCP와 Extension의 역할 차이

앞 절에서 본 Tableau MCP와 Tableau Extension은 자주 함께 쓰이지만, 역할은 분명히 다릅니다.

### 3-1. 한 줄 차이

- MCP: `AI가 Tableau를 읽고 실행할 수 있게 하는 연결 계층`
- Extension: `그 결과를 Tableau 화면 안에서 보여주고 상호작용하게 하는 UI 계층`

즉:

```text
사용자 클릭
  ↓
Tableau Dashboard
  ↓
Extension (대시보드 안의 웹 UI)
  ↓
Backend / MCP / LLM / 외부 API
  ↓
결과를 다시 Extension 패널에 표시
```

이 구조로 이해하시면 됩니다.

### 3-2. 왜 둘을 같이 쓰면 강력한가

MCP만 있으면 AI가 Tableau 밖에서 데이터를 읽고 설명할 수 있습니다.  
반대로 Extension만 있으면 Tableau 안에 예쁜 패널은 붙일 수 있지만, 실제로 어떤 데이터를 읽고 어떤 도구를 호출할지에 대한 지능형 연결은 별도로 설계해야 합니다.

둘을 함께 쓰면:

- Tableau 안에서 사용자가 마크를 클릭하고
- Extension이 그 선택 상태를 읽고
- MCP나 백엔드 서비스가 데이터를 조회하고
- LLM이 맥락을 요약한 뒤
- 결과를 다시 Tableau 안 패널에 보여주는

흐름이 완성됩니다.

즉, `MCP는 두뇌와 도구 연결`, `Extension은 사용자 접점`이라고 이해하시면 훨씬 쉽습니다.

## 4. AI와 결합하면 무엇을 만들 수 있을까?

Tableau Extension의 진짜 매력은 "차트 옆에 외부 맥락과 행동(Action)을 붙일 수 있다"는 점입니다.

### 4-1. 데이터 스토리 패널

가장 직관적인 예시는 `인사이트 요약 패널`입니다.

- 대시보드가 보여주는 현재 필터 상태
- 선택된 차트의 마크
- 주요 KPI 변화

를 읽어, AI가 "지금 화면에서 무엇이 중요한지"를 자연어로 설명해 줄 수 있습니다.

이 방식은 사용자가 대시보드를 읽는 부담을 줄여 줍니다.  
특히 분석 경험이 적은 현업 사용자에게는 `차트를 보는 것`보다 `차트를 해석해 주는 것`이 더 큰 가치가 될 수 있습니다.

### 4-2. 외부 뉴스/시장 데이터 연결

주가 예시가 아주 좋습니다.

- 사용자가 특정 종목의 급락 날짜를 클릭
- Extension이 종목명과 날짜를 읽음
- 외부 뉴스 검색 API를 호출
- AI가 당시 맥락을 요약
- 관련 기사 링크를 함께 표시

이 패턴의 핵심은 `내부 차트의 특정 지점`과 `외부 데이터의 사건 맥락`을 연결한다는 점입니다.

실무에서는 다음처럼 확장할 수 있습니다.

- 매출 급감 시점과 업계 뉴스 연결
- CS 폭증 날짜와 장애 공지/소셜 반응 연결
- 광고 성과 급등일과 캠페인 집행 이력 연결

즉, 대시보드가 "무슨 일이 일어났는지"를 보여준다면, Extension은 "왜 그런 일이 일어났는지"에 대한 실마리를 붙여 줄 수 있습니다.

### 4-3. Viz Advisor 같은 시각화 코치

분석 목적을 입력하면:

- 어떤 차트가 적합한지 추천하고
- 왜 그 차트가 적합한지 설명하고
- Tableau에서 어떻게 그릴지 단계까지 안내하는

형태도 Extension에 잘 어울립니다.

이런 기능은 단순 자동화가 아니라 `시각화 사고를 보조하는 학습 도구`라는 점에서 의미가 큽니다.

즉, 익스텐션은 단지 결과 화면이 아니라 `실무자와 학습자를 위한 인터랙티브 코치`가 될 수 있습니다.

### 4-4. Data-to-Deck 같은 후속 액션

분석의 끝이 늘 대시보드 감상에서 끝나는 것은 아닙니다.  
실무에서는 결국:

- 보고서 작성
- 발표 자료 생성
- 회의용 요약 정리

가 이어집니다.

이때 Extension은 대시보드 안에서 버튼 하나로:

- 현재 선택한 시트 목록
- 필터 상태
- 핵심 메시지
- 사용자 추가 코멘트

를 모아 백엔드로 보내고, AI가 PPT 초안이나 요약 문서를 생성하게 만들 수 있습니다.

즉, Extension은 `분석 결과를 다음 업무 행위로 넘기는 작업 허브`가 될 수 있습니다.

## 5. Tableau Extension 개발의 기본 흐름

개발 흐름은 생각보다 단순합니다.

### 5-1. 웹 화면을 만든다

우선 HTML/JavaScript 기반 웹 화면을 만듭니다.  
React, Vue, Vanilla JS 어떤 방식이든 상관없습니다.

중요한 것은 이 화면이:

- Tableau 안의 작은 패널에서도 잘 보이고
- 비동기 호출 결과를 자연스럽게 보여주고
- 로딩/오류 상태를 잘 처리하는 것

입니다.

### 5-2. Extensions API를 초기화한다

웹 화면 안에서는 먼저 Extensions API를 초기화해야 합니다.

```javascript
await tableau.extensions.initializeAsync();

const dashboard = tableau.extensions.dashboardContent.dashboard;
const worksheet = dashboard.worksheets.find(
  sheet => sheet.name === "주가 추이"
);
```

이 단계가 끝나야 현재 대시보드, 워크시트, 필터, 파라미터, 선택 마크 등에 접근할 수 있습니다.

### 5-3. 사용자 상호작용 이벤트를 받는다

예를 들어 사용자가 차트의 특정 마크를 클릭했을 때 반응하고 싶다면 다음처럼 이벤트를 걸 수 있습니다.

```javascript
worksheet.addEventListener(
  tableau.TableauEventType.MarkSelectionChanged,
  async () => {
    const marks = await worksheet.getSelectedMarksAsync();
    // 선택된 종목, 날짜 등을 추출
    // 외부 API 또는 LLM 백엔드 호출
    // 결과를 패널에 렌더링
  }
);
```

즉, 익스텐션은 단순한 고정 화면이 아니라 `대시보드의 상호작용을 감지하는 반응형 앱`입니다.

### 5-4. 필요하면 데이터 접근 권한을 선언한다

요약 데이터나 선택 마크 정도가 아니라, 원본 수준 데이터나 데이터 원본 정보를 읽으려면 `full data` 권한을 선언해야 합니다.

이 부분이 왜 중요하냐면:

- 선언이 없으면 관련 API 호출이 실패할 수 있고
- 사용자에게 권한 허용 프롬프트가 뜨며
- 운영 환경에서는 관리자 승인까지 연결될 수 있기 때문입니다.

즉, "코드가 돌아가느냐"의 문제가 아니라 `거버넌스와 신뢰`의 문제이기도 합니다.

### 5-5. `.trex`로 등록하고 대시보드에 올린다

이제 `.trex` 파일을 만든 뒤 Tableau에서:

- 대시보드 열기
- `Objects` 영역에서 `Extension` 드래그
- `Access Local Extensions` 선택
- `.trex` 파일 지정

순서로 추가하면 됩니다.

한 번 붙고 나면, 기존 웹 앱이 Tableau 안에서 동작하는 형태가 됩니다.

## 6. 실무에서 주의할 점

Extension은 강력하지만, 실제 운영 단계에서는 몇 가지 함정이 있습니다.

### 6-1. 보안과 관리자 승인

Extension은 본질적으로 웹 애플리케이션입니다.  
즉, 단순 차트 객체가 아니라 외부 네트워크와 통신할 수 있는 코드입니다.

그래서 실무에서는 아래가 중요합니다.

- Tableau Cloud / Server에서 Extension 실행 허용 여부
- Network-enabled Extension의 allow list 등록
- 어떤 URL과 어떤 데이터 접근 권한을 허용할지 검토

특히 AI 기능을 붙이면 외부 LLM API, 사내 백엔드, 뉴스 검색 API 등과 연결될 가능성이 높기 때문에 보안 검토 없이 배포하면 운영 단계에서 바로 막히기 쉽습니다.

### 6-2. 내보내기와 구독 메일 한계

아주 중요한 실무 포인트가 하나 있습니다.

Tableau Server나 Tableau Cloud에서는 `대시보드의 Extension 영역이 PDF, 이미지, 인쇄물, 구독 메일 이미지에서 비어 보일 수 있습니다.`

왜 문제가 되냐면:

- 화면에서는 멀쩡한데
- 경영진에게 전달된 PDF에는 핵심 AI 패널이 빠지고
- 구독 메일 이미지에도 중요한 설명이 사라질 수 있기 때문입니다.

즉, Extension 안의 내용을 `유일한 설명 채널`로 설계하면 전달물 단계에서 문제가 생길 수 있습니다.

그래서 실무에서는:

- 핵심 KPI와 핵심 차트 해석은 대시보드 본체에도 남기고
- Extension은 보조 설명, 탐색, 후속 액션 역할로 두는 것

이 안전합니다.

### 6-3. 성능 설계

사용자가 클릭할 때마다:

- 전체 원본 데이터를 다시 읽고
- 외부 API를 여러 번 호출하고
- LLM 응답을 오래 기다리게 하면

대시보드 경험이 금방 답답해집니다.

그래서 보통은 다음 우선순위를 권장합니다.

1. 먼저 선택 마크와 요약 데이터만 사용
2. 꼭 필요할 때만 원본 데이터 접근
3. 긴 작업은 비동기 로딩 UI로 분리
4. 자주 쓰는 결과는 캐시

즉, Extension은 "작은 앱"이지만 성능 설계는 일반 웹 서비스처럼 다뤄야 합니다.

### 6-4. UX 역할을 과하게 키우지 않기

Extension이 신기하다고 해서 모든 기능을 그 안에 몰아넣으면 오히려 분석이 어려워질 수 있습니다.

대시보드의 본질은 여전히:

- 핵심 지표를 빠르게 파악하고
- 비교와 드릴다운을 수행하고
- 이상 신호를 발견하는 것

입니다.

따라서 Extension은 보통 아래 역할일 때 가장 효과적입니다.

- 맥락 설명
- 외부 데이터 연결
- 액션 실행
- 학습/가이드 제공

즉, `대시보드를 대체하는 앱`이 아니라 `대시보드를 더 똑똑하게 만드는 조력자`로 설계하는 것이 좋습니다.

## 정리

Tableau Extension은 단순한 부가 기능이 아니라, `Tableau를 데이터 연결이 이미 끝난 개발 도화지`로 바꿔 주는 장치입니다.

- MCP가 AI와 Tableau를 연결하는 실행 통로라면
- Extension은 그 결과를 대시보드 안의 사용자 경험으로 바꾸는 방법입니다.

따라서 앞으로는 Tableau를 "차트를 만드는 툴"로만 보기보다:

- AI 인사이트 패널
- 외부 맥락 연결 패널
- 문서/보고 자동화 버튼
- 시각화 코치

같은 아이디어를 실험할 수 있는 `분석 인터페이스 플랫폼`으로 바라보셔도 좋습니다.

## 참고 자료

- [Tableau Extensions API 문서](https://tableau.github.io/extensions-api/docs/)
- [Tableau Extension Manifest (.trex) 문서](https://tableau.github.io/extensions-api/docs/dashext/trex_manifest/)
- [Use Dashboard Extensions - Tableau Help](https://help.tableau.com/current/pro/desktop/en-us/dashboard_extensions.htm)
- [tableau/extensions-api GitHub](https://github.com/tableau/extensions-api)
