# 📊 태블로를 활용한 데이터 시각화

> **Tableau를 처음 배우는 입문자부터 실무에서 더 설득력 있는 대시보드를 만들고 싶은 분석가까지 함께 읽을 수 있는 Tableau 입문서입니다.**

---

## 📖 이 책에 대하여

이 책은 Tableau의 기능을 단순히 나열하는 방식으로 구성되지 않았습니다.  
**비즈니스 인텔리전스(BI)의 맥락** 안에서 Tableau를 이해하고, 데이터를 어떻게 읽고 해석하며, 어떤 방식으로 시각화해야 더 나은 의사결정으로 이어지는지를 함께 다룹니다.

이 책의 중심에는 단순한 조작법이 아니라 **분석의 흐름**이 있습니다.

- ❌ "어디를 클릭해야 하는가"를 외우는 책이 아닙니다.
- ✅ "왜 이 차트를 선택해야 하는가", "왜 이 계산이 필요한가", "왜 이 대시보드 구성이 더 효과적인가"를 함께 익히는 책입니다.

---

## 🎯 이런 독자에게 추천합니다

| 독자 유형 | 이 책이 도움이 되는 이유 |
|---|---|
| Tableau 입문자 | 설치부터 대시보드 공유까지 전체 흐름을 따라갈 수 있습니다 |
| 엑셀 중심 실무자 | BI 도구 기반 분석으로 전환하는 방법을 익힐 수 있습니다 |
| 데이터 분석가 | 차트 제작을 넘어 해석 가능한 대시보드를 설계하는 법을 배웁니다 |
| 기획자 / 운영 담당자 | 여러 데이터를 하나의 화면에서 설득력 있게 보여주는 법을 익힙니다 |

특히 이 책은 **"차트를 만드는 사람"보다 "데이터를 설명해야 하는 사람"** 에게 더 잘 맞습니다.

---

## 📚 책의 구성 (총 5챕터)

```
📦 tableau-book
 ├── 📁 1. Tableau 기초
 │   ├── 1-1. 비즈니스 인텔리전스란
 │   ├── 1-2. Tableau 소개
 │   ├── 1-3. Tableau Desktop 설치 및 라이선스 활성화
 │   └── 1-4. Tableau 기초
 ├── 📁 2. 데이터 시각화
 │   ├── 2-1. 다양한 차트 시각화
 │   ├── 2-2. 분석을 위한 다양한 기능 활용
 │   ├── 2-3. 이중축을 활용한 시각화
 │   └── 2-4. 대시보드 저장 및 공유
 ├── 📁 3. 데이터 계산 및 함수
 │   ├── 3-1. 데이터 필드 생성 및 활용
 │   ├── 3-2. 계산된 필드와 계산 수준
 │   ├── 3-3. 매개변수와 계산식
 │   └── 3-4. 계산식 주요 함수 정리
 ├── 📁 4. 데이터 결합, 정리, 변형
 │   ├── 4-1. Tableau Prep을 활용한 데이터 전처리
 │   ├── 4-2. 태블로 작업 순서와 라이브 vs 추출
 │   └── 4-3. 데이터 원본 편집
 └── 📁 5. 대시보드 구축 및 공유
     ├── 5-1. 대시보드 소개
     ├── 5-2. 대시보드 화면 구성 및 디자인
     ├── 5-3. 대시보드 구성 실습
     ├── 5-4. 대시보드 동작 및 도구 설명
     └── 5-5. Tableau Cloud를 통한 대시보드 공유
```

전체 목차는 [TOC.md](./TOC.md)에서 확인할 수 있습니다.

---

## 🗂️ 챕터별 주요 내용

### 1장 · Tableau 기초

- **Visual Analytics** : 사람이 시각 정보를 더 빠르게 인식하는 원리와 시각화가 필요한 이유
- **BI 개념과 대표 도구** : Power BI, Looker Studio와의 비교표 포함
- **Tableau 제품군** : Desktop · Prep · Server · Cloud의 역할과 흐름
- **라이선스 종류** : Creator / Explorer / Viewer 비교
- **설치 실습** : Tableau Cloud 계정 생성, MFA 인증(Salesforce / Google Authenticator), Desktop 활성화
- **Tableau Public** : 무료 버전과 유료 버전의 차이 비교표
- **UI 완전 정복** : 데이터 패널, 선반, 마크 카드, 분석 패널 등 12개 영역 설명
- **차원 vs 측정값** : Superstore 실습 데이터로 개념 체득

### 2장 · 데이터 시각화

- **차트 3가지 생성 방법** : 더블클릭 / 드래그 앤 드롭 / 표현 방식(Show Me)
- **기본 차트 실습** : 막대, 라인, 맵, 파이, 트리맵, 버블, 워드 클라우드
- **연속형 vs 불연속형 날짜** : 같은 날짜 필드가 차트 구조를 어떻게 다르게 만드는지
- **퀵 테이블 계산** : 누계, 차이, 구성 비율, 전년 대비 성장률 등 11가지
- **KPI 카드 시각화** : 총 매출 · 총 수익 · 총 주문 · 총 고객 단계별 실습
- **정렬 4가지** : 아이콘 / 축 / 차원 / 중첩 정렬
- **필터 심화** : 동적 vs 정적 필터, 적용 범위(워크시트/데이터 원본/대시보드)
- **크로스탭 & 히트맵** : 정확한 수치 확인 vs 패턴 탐색 구분 활용
- **스캐터 차트** : 추세선, 클러스터, 이상치 탐색
- **분석 패널** : 참조선, 추세선, 박스 플롯, 예측, K-means 클러스터링
- **이중축** : 도넛 차트, 나비 차트 등 고급 시각화 구현
- **저장 및 공유** : `.twb` vs `.twbx` 차이, Tableau Public 게시, Cloud 공유, Notion 임베드

### 3장 · 데이터 계산 및 함수

- **그룹, 빈, 집합** : 정적/동적 집합, 집합 동작(Set Action), 드릴다운 구현
- **Measure Names / Measure Values** 활용법
- **계산된 필드** : 임시 계산 vs 정식 계산, 필드 네이밍 규칙(`C_`, `P_`, `FLTR_`)
- **행 수준 vs 집계 수준 계산** : `[수익]/[매출]` vs `SUM([수익])/SUM([매출])` 차이 비교 실습
- **LOD(Level of Detail)** 표현식 : FIXED · INCLUDE · EXCLUDE 개념과 활용 시점
- **매개변수** : 차원 매개변수 · 측정값 매개변수, 전년도 대비(YoY) KPI 실습
- **주요 함수 정리** : 문자열, 날짜, 논리, 집계, LOD 함수 카탈로그
- **GPT를 활용한 계산식 작성** 팁

### 4장 · 데이터 결합, 정리, 변형

- **Tableau Prep** : 전처리 시간의 80% 문제 해결, 시각적 흐름 설계
- **유니온 vs 조인** : 수직 결합(행 추가) vs 수평 결합(열 추가) 비교
- **4개년 파일 유니온 실습** : 컬럼 불일치 자동 탐지 및 필드 병합
- **관리자 정보 조인** : 키 값 표준화 문제 해결 (`서울경기` → `수도권`)
- **반품 현황 LEFT JOIN** : 내부 조인 vs 왼쪽 조인 선택 실수 방지
- **출력 포맷** : `.hyper` 파일로 Desktop에 연결
- **라이브 vs 추출** : 실시간 연결과 성능 차이, 증분 새로 고침
- **Tableau 작업 순서(Order of Operations)** : 필터 우선순위와 컨텍스트 필터
- **데이터 원본 편집** : 관계(Relationship), 조인, 유니온, 블렌딩 비교표, 데이터 원본 교체

### 5장 · 대시보드 구축 및 공유

- **대시보드 설계 원리** : 레이아웃, 여백, 정렬, 색상 일관성
- **컨테이너 활용** : 수평/수직 컨테이너 중첩, 타일 vs 부동 배치
- **대시보드 동작(Actions)** : 필터 동작, 하이라이트 동작, URL 동작
- **도구 설명** : 호버 시 상세 정보 표시 및 비주이저 인 툴팁
- **Tableau Cloud 공유** : 게시, 권한 설정, 구독, 알림, 댓글

---

## 🛠️ 실습 데이터

모든 실습은 **한국형 Superstore 샘플 데이터(KR Superstore Sample 2025)** 를 사용합니다.

| 항목 | 내용 |
|---|---|
| 데이터셋 | 가상의 소매점 판매 데이터 |
| 주요 필드 | 주문 번호, 주문/배송 일자, 고객 정보, 제품 분류, 매출/수익/할인율 |
| 지역 | 대한민국 (시도, 시군구) |
| 기간 | 2021 ~ 2024년 (4개년) |

**📥 데이터 다운로드:**  
[Kaggle - KR Superstore Sample 2025](https://www.kaggle.com/datasets/heoquixote/krsuperstore-sample-2025/data)

> Kaggle 계정이 없는 경우 무료로 가입한 후 다운로드할 수 있습니다.

---

## 🚀 읽기 전에 준비하세요

### Tableau 설치

이 책의 실습을 따라하려면 Tableau가 설치되어 있어야 합니다.

**① Tableau Desktop (유료 / 학생 무료 제공)**
```
https://www.tableau.com/ko-kr/support/releases
```

**② Tableau Desktop Public Edition (무료)**
```
https://public.tableau.com/app/discover
```

| 구분 | Tableau Desktop Public Edition | Tableau Desktop |
|---|---|---|
| 가격 | 무료 | 유료 (Creator 라이선스) |
| 저장 위치 | Tableau Public에만 공개 저장 | 로컬 / Cloud / Server |
| 데이터 연결 | Excel, CSV, Google Sheets 등 제한 | DB, 클라우드 포함 전체 |
| 활용 목적 | 학습, 포트폴리오 | 기업 분석, 실무 |

> 💡 처음 시작하는 분이라면 **Public Edition**으로 시작해도 충분합니다.

### Tableau Prep 설치 (4장 실습 시 필요)
```
https://www.tableau.com/ko-kr/support/releases/prep
```

---

## 🗺️ 저장소 구조

```
tableau-book/
├── README.md          # 이 파일
├── TOC.md             # 전체 목차
├── pages/             # 챕터별 본문 원고
│   ├── 01-tableau-basics.md
│   ├── 01-1-bi-overview.md
│   ├── 01-2-tableau-introduction.md
│   ├── ...
│   └── 05-5-tableau-cloud-sharing.md
├── assets/            # 본문에 사용되는 이미지 파일
│   ├── book-cover.png
│   └── ...
└── examples/          # 실습 예제 파일
```

- **본문 원고** → [`pages/`](./pages/) 폴더에서 챕터/절 단위로 확인할 수 있습니다.
- **이미지 자료** → [`assets/`](./assets/) 폴더에 파일명 기준(챕터-절 접두어)으로 정리되어 있습니다.

---

## 📋 전체 목차 바로가기

> 각 링크를 클릭하면 해당 절의 본문으로 바로 이동합니다.

### 1장. Tableau 기초

| 절 | 주요 내용 |
|---|---|
| [1-1. 비즈니스 인텔리전스란](pages/01-1-bi-overview.md) | Visual Analytics, BI 개념, 대표 BI 도구 비교 |
| [1-2. Tableau 소개](pages/01-2-tableau-introduction.md) | Tableau 역사, 제품군, 라이선스, Why Tableau? |
| [1-3. 설치 및 라이선스 활성화](pages/01-3-install-and-license.md) | Cloud 계정 생성, MFA 인증, Desktop 설치 |
| [1-4. Tableau 기초](pages/01-4-tableau-basics-practice.md) | UI 구조, 차원 vs 측정값, 데이터 연결 |

### 2장. 데이터 시각화

| 절 | 주요 내용 |
|---|---|
| [2-1. 다양한 차트 시각화](pages/02-1-chart-visualization.md) | 막대, 라인, 맵, 파이, 트리맵, KPI 카드 |
| [2-2. 분석을 위한 다양한 기능 활용](pages/02-2-analysis-features.md) | 정렬, 필터, 크로스탭, 스캐터, 분석 패널 |
| [2-3. 이중축을 활용한 시각화](pages/02-3-dual-axis-visualization.md) | 이중축, 도넛 차트, 나비 차트 |
| [2-4. 대시보드 저장 및 공유](pages/02-4-save-and-share-dashboard.md) | twb vs twbx, 내보내기, Tableau Public 게시 |

### 3장. 데이터 계산 및 함수

| 절 | 주요 내용 |
|---|---|
| [3-1. 데이터 필드 생성 및 활용](pages/03-1-field-creation.md) | 그룹, 빈, 집합, Set Action, 지리 역할 |
| [3-2. 계산된 필드와 계산 수준](pages/03-2-calculated-fields-and-lod.md) | 행 수준 vs 집계 수준, LOD 표현식 |
| [3-3. 매개변수와 계산식](pages/03-3-parameters-and-calculations.md) | 매개변수 생성, YoY KPI, 성장률 계산 |
| [3-4. 계산식 주요 함수 정리](pages/03-4-core-functions.md) | 문자열, 날짜, 논리, 집계, LOD 함수 |

### 4장. 데이터 결합, 정리, 변형

| 절 | 주요 내용 |
|---|---|
| [4-1. Tableau Prep 전처리](pages/04-1-tableau-prep.md) | Prep 설치, 유니온, 조인, 필드 정리, 출력 |
| [4-2. 라이브 vs 추출](pages/04-2-live-vs-extract.md) | 연결 방식 차이, 작업 순서, 컨텍스트 필터 |
| [4-3. 데이터 원본 편집](pages/04-3-data-source-editing.md) | 관계/블렌딩 비교, 데이터 원본 교체 |

### 5장. 대시보드 구축 및 공유

| 절 | 주요 내용 |
|---|---|
| [5-1. 대시보드 소개](pages/05-1-dashboard-introduction.md) | 대시보드의 역할과 구성 원리 |
| [5-2. 화면 구성 및 디자인](pages/05-2-dashboard-layout-and-design.md) | 레이아웃, 컨테이너, 디자인 원칙 |
| [5-3. 대시보드 구성 실습](pages/05-3-dashboard-workshop.md) | 단계별 대시보드 제작 실습 |
| [5-4. 동작 및 도구 설명](pages/05-4-dashboard-actions-and-tools.md) | 필터/하이라이트/URL 동작, 도구 설명 |
| [5-5. Tableau Cloud 공유](pages/05-5-tableau-cloud-sharing.md) | 게시, 권한, 구독, 협업 |

---

## 💡 이 책을 읽는 방법

### 처음 배우는 분이라면
1→2→3→4→5장 순서로 읽으세요. 전체 분석 흐름을 한 권 안에서 따라갈 수 있습니다.

### Tableau를 이미 쓰고 있는 분이라면
관심 있는 챕터부터 바로 펼쳐도 됩니다. 각 절은 독립적으로 읽을 수 있도록 구성되어 있습니다.

### 실습 중심으로 배우고 싶은 분이라면
- 먼저 [실습 데이터를 다운로드](https://www.kaggle.com/datasets/heoquixote/krsuperstore-sample-2025/data)하세요.
- `[실습]` 태그가 붙은 절들을 따라가며 직접 만들어 보세요.

> 💬 **Tip**: 각 절 마지막의 **정리** 섹션만 먼저 훑어보면 전체 내용을 빠르게 파악하는 데 도움이 됩니다.

---

## 🔗 유용한 외부 링크

| 링크 | 설명 |
|---|---|
| [Tableau Public](https://public.tableau.com/app/discover) | 무료 Tableau 설치 및 커뮤니티 대시보드 탐색 |
| [Tableau 공식 문서](https://help.tableau.com/current/pro/desktop/ko-kr/default.htm) | 기능별 공식 레퍼런스 |
| [Tableau 릴리스 페이지](https://www.tableau.com/ko-kr/support/releases) | Desktop 버전별 다운로드 |
| [KR Superstore Dataset (Kaggle)](https://www.kaggle.com/datasets/heoquixote/krsuperstore-sample-2025/data) | 실습용 데이터셋 |
| [Tableau Minesweeper 예시](https://public.tableau.com/app/profile/edwardhayter/viz/ExpertMinesweeper/Minesweeper) | Tableau 시각화 자유도를 보여주는 극단적 예시 |

---

## 📌 표지

책 표지 파일은 [`assets/book-cover.png`](./assets/book-cover.png)에서 확인할 수 있습니다.
