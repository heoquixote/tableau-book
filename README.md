# 태블로를 활용한 데이터 시각화

Tableau 입문부터 대시보드 설계, 데이터 계산, Tableau Cloud 공유까지 한 흐름으로 정리한 원고 저장소입니다.  
기능을 단순히 나열하기보다, 실무에서 왜 이 기능을 쓰는지와 어떤 상황에서 문제가 생기는지까지 함께 설명하는 방향으로 구성했습니다.

## 이 저장소에서 다루는 내용

- Tableau 기초와 BI 관점 이해
- 차트 작성과 분석 기능 활용
- 계산된 필드, LOD, 매개변수, 주요 함수
- 데이터 결합, 전처리, 라이브 vs 추출
- 대시보드 설계, 구성, 액션, Tooltip
- Tableau Cloud를 통한 게시와 협업

## 이런 분께 맞습니다

- Tableau를 처음 배우는 분
- Excel 중심 보고에서 BI 도구 기반 분석으로 넘어가려는 분
- 차트 작성보다 “좋은 대시보드 설계”를 더 잘하고 싶은 분
- Tableau Cloud까지 포함해 공유와 운영 흐름을 익히고 싶은 분

## 도서 구성

### 01. Tableau 기초

BI가 왜 필요한지, 시각화가 왜 중요한지부터 시작합니다.  
이 장에서는 Tableau라는 도구를 단순히 소개하는 데서 끝나지 않고, 제품군 구조, 라이선스, 설치와 인증 흐름, 기본 화면 구성까지 한 번에 정리합니다.

주요 내용:

- 시각적 분석(Visual Analytics)과 BI의 기본 개념
- 대표적인 BI 도구 비교와 Tableau의 위치
- Tableau 제품군, 구조, 라이선스 이해
- Tableau Cloud 계정 활성화와 Desktop 설치
- 데이터 연결, 필드 아이콘, 차원과 측정값 이해

### 02. 데이터 시각화

Tableau에서 가장 많이 쓰는 기본 차트와 분석 기능을 익히는 장입니다.  
막대, 라인, 맵, 파이, 트리맵 같은 기본 차트부터 KPI 카드, 정렬, 필터, 크로스탭, 스캐터 차트, 이중축까지 이어집니다.

주요 내용:

- Tableau 시각화 방법과 주요 차트 실습
- 연속형/불연속형 날짜 차이
- 계층 만들기와 퀵 테이블 계산
- KPI 카드 시각화
- 정렬, 필터, 대시보드 필터 표시
- 크로스탭, 히트맵, 스캐터 차트, 분석 패널
- 이중축, 도넛 차트, 버터플라이 차트
- 저장, 내보내기, Tableau Public/Cloud 공유

### 03. 데이터 계산 및 함수

단순 차트 작성에서 더 나아가, 계산을 통해 분석을 정교하게 만드는 장입니다.  
그룹, 집합, 히스토그램 같은 기본 필드 생성부터 계산된 필드, 행 수준 계산과 집계 수준 계산, 매개변수, 주요 함수까지 다룹니다.

주요 내용:

- 그룹과 집합, 집합 기반 드릴다운 분석
- 구간 차원과 히스토그램
- Measure Names / Measure Values 활용
- 계산된 필드 작성과 계산식 구조 이해
- 행 수준 계산과 집계 수준 계산 비교
- 매개변수와 계산식을 활용한 동적 뷰 구성
- 전년 대비 KPI 계산
- 문자열, 숫자, 날짜, 순위 함수와 LOD 표현식

### 04. 데이터 결합, 정리, 변형

분석 전에 데이터를 어떤 형태로 준비해야 하는지 다루는 장입니다.  
Tableau Prep을 이용한 유니온, 조인, 필드 정리부터 라이브와 추출 차이, 필터 적용 순서, 관계/조인/유니온/블렌딩까지 연결합니다.

주요 내용:

- Tableau Prep 소개와 설치
- 다년도 파일 유니온과 불일치 컬럼 정리
- 조인, 불필요 필드 제거, 출력
- 라이브 vs 추출 연결 방식 비교
- Tableau 작업 순서와 필터 적용 순서
- 관계, 조인, 유니온, 블렌딩 개념 비교
- 통합 문서 합치기
- 데이터 원본 바꾸기와 참조 바꾸기

### 05. 대시보드 구축 및 공유

앞에서 만든 시트와 계산을 실제 대시보드로 묶고, 사용자와 공유하는 단계까지 다루는 장입니다.  
대시보드의 역할과 목적을 이해한 뒤, 화면 설계와 디자인, Tableau Desktop에서의 레이아웃 구성, 액션과 Tooltip, Tableau Cloud 게시와 협업까지 이어집니다.

주요 내용:

- 대시보드의 개념, 목적, 유형, 산업별 예시
- 비즈니스 질문 기반 화면 설계와 디자인 원칙
- 장치별 레이아웃, 대시보드 크기, 컨테이너와 개체
- 액션, Tooltip, Viz in Tooltip, Dynamic Zone Visibility
- Tableau Cloud 게시, 공유, 댓글, 구독, 알림
- 권한 관리와 버전 관리

상세 목차는 [TOC.md](./TOC.md)에서 확인할 수 있습니다.

## 실습 데이터

대부분의 예제는 `KR Superstore Sample 2025`를 기반으로 작성했습니다.

- 기간: 2021년 ~ 2024년
- 주제: 한국형 가상 소매점 데이터
- 주요 영역: 주문, 고객, 제품, 지역, 매출, 수익, 반품 등

다운로드:
[Kaggle - KR Superstore Sample 2025](https://www.kaggle.com/datasets/heoquixote/krsuperstore-sample-2025/data)

## 실습 전 준비

### Tableau Desktop

```text
https://www.tableau.com/ko-kr/support/releases
```

### Tableau Public

```text
https://public.tableau.com/app/discover
```

### Tableau Prep

4장 전처리 실습까지 진행하려면 Tableau Prep도 함께 설치하는 것이 좋습니다.

```text
https://www.tableau.com/ko-kr/support/releases/prep
```

## 저장소 구조

```text
tableau-book/
├── README.md
├── TOC.md
├── pages/
├── assets/
└── examples/
```

- `pages/`: 장/절별 원고
- `assets/`: 본문에 들어가는 이미지와 도해
- `examples/`: 예제용 Tableau 파일

## 추천 학습 순서

### 처음부터 차근차근 보는 경우

1장부터 5장까지 순서대로 읽는 것을 추천합니다.  
설치 → 시각화 → 계산 → 데이터 준비 → 대시보드 → 공유 흐름으로 이어집니다.

### 필요한 주제만 찾는 경우

아래 문서를 바로 보시면 됩니다.

- 시각화: [2장](./pages/02-data-visualization.md)
- 계산식: [3장](./pages/03-calculation-and-functions.md)
- 데이터 준비: [4장](./pages/04-data-preparation.md)
- 대시보드: [5장](./pages/05-dashboard-build-and-share.md)

### 실습 위주로 보는 경우

- `pages/` 안에서 `[실습]`이 포함된 절부터 먼저 따라가면 됩니다.
- 데이터는 먼저 내려받아 두는 편이 좋습니다.
- 4장은 Tableau Prep, 5장은 Tableau Desktop과 Tableau Cloud 환경이 있으면 가장 자연스럽게 따라갈 수 있습니다.

## 문서 링크

### 1장. Tableau 기초

- [1-1. 비즈니스 인텔리전스란](./pages/01-1-bi-overview.md)
- [1-2. Tableau 소개](./pages/01-2-tableau-introduction.md)
- [1-3. Tableau Desktop 설치 및 라이선스 활성화](./pages/01-3-install-and-license.md)
- [1-4. Tableau 기초](./pages/01-4-tableau-basics-practice.md)

### 2장. 데이터 시각화

- [2-1. 다양한 차트 시각화](./pages/02-1-chart-visualization.md)
- [2-2. 분석을 위한 다양한 기능 활용](./pages/02-2-analysis-features.md)
- [2-3. 이중축을 활용한 시각화](./pages/02-3-dual-axis-visualization.md)
- [2-4. 대시보드 저장 및 공유](./pages/02-4-save-and-share-dashboard.md)

### 3장. 데이터 계산 및 함수

- [3-1. 데이터 필드 생성 및 활용](./pages/03-1-field-creation.md)
- [3-2. 계산된 필드와 계산 수준](./pages/03-2-calculated-fields-and-lod.md)
- [3-3. 매개변수와 계산식](./pages/03-3-parameters-and-calculations.md)
- [3-4. 계산식 주요 함수 정리](./pages/03-4-core-functions.md)

### 4장. 데이터 결합, 정리, 변형

- [4-1. Tableau Prep을 활용한 데이터 전처리](./pages/04-1-tableau-prep.md)
- [4-2. 태블로 작업 순서와 라이브 vs 추출](./pages/04-2-live-vs-extract.md)
- [4-3. 데이터 원본 편집](./pages/04-3-data-source-editing.md)

### 5장. 대시보드 구축 및 공유

- [5-1. 대시보드 소개](./pages/05-1-dashboard-introduction.md)
- [5-2. 대시보드 화면 구성 및 디자인](./pages/05-2-dashboard-layout-and-design.md)
- [5-3. 대시보드 구성 실습](./pages/05-3-dashboard-workshop.md)
- [5-4. 대시보드 동작 및 도구 설명](./pages/05-4-dashboard-actions-and-tools.md)
- [5-5. Tableau Cloud를 통한 대시보드 공유](./pages/05-5-tableau-cloud-sharing.md)
