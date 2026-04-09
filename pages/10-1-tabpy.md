## 학습 목표

- TabPy가 Tableau에서 어떤 역할을 하는지 설명할 수 있습니다.
- Analytics Extension과 TabPy의 관계를 이해할 수 있습니다.
- Tableau 안에서 해결하기 어려운 계산을 언제 Python으로 넘겨야 하는지 판단할 수 있습니다.

## 목차

1. TabPy란?
2. 어떻게 연결되는가?
3. 언제 유용한가?
4. 실무에서 주의할 점

## 1. TabPy란?

TabPy는 Tableau가 Python과 연결될 수 있도록 해주는 Analytics Extension입니다.  
Tableau 자체 계산식으로 처리하기 어려운 통계, 예측, 사용자 정의 로직을 Python 쪽으로 넘겨 계산한 뒤 결과를 다시 Tableau로 가져오는 방식으로 사용합니다.

즉, TabPy는 Tableau를 Python으로 대체하는 기능이 아니라, `Tableau 시각화 + Python 계산`을 연결하는 다리라고 이해하시면 됩니다.

## 2. 어떻게 연결되는가?

Tableau는 Analytics Extension 연결을 통해 외부 서비스와 통신합니다.  
공식 문서 기준으로 Tableau Desktop과 Tableau Cloud/Tableau Server 웹 작성 환경에서는 Analytics Extension 연결을 만들 수 있고, 이때 TabPy를 연결 대상으로 선택할 수 있습니다.

실무 흐름은 보통 다음과 같습니다.

1. Python 환경에서 TabPy 서버를 실행합니다.
2. Tableau에서 `Manage Analytics Extension Connection`으로 TabPy 연결을 설정합니다.
3. 계산된 필드에서 `SCRIPT_*` 계열 함수를 사용해 Python으로 값을 전달합니다.
4. Python이 결과를 반환하면 Tableau가 이를 시각화에 사용합니다.

핵심은 TabPy가 직접 차트를 만드는 것이 아니라, `계산 결과만 반환`한다는 점입니다.

## 3. 언제 유용한가?

TabPy는 다음과 같은 경우에 특히 유용합니다.

- Tableau 기본 함수로 구현하기 어려운 통계 계산이 필요할 때
- Python 라이브러리 기반 예측 모델이나 점수화를 적용할 때
- 문자열/숫자/날짜 함수 수준을 넘어서는 사용자 정의 로직이 필요할 때
- 이미 Python으로 만들어 둔 분석 코드를 Tableau 시각화에 연결하고 싶을 때

예를 들어 다음과 같은 시나리오에서 자주 검토합니다.

- 고객 이탈 확률 점수 계산
- 이상치 탐지
- 회귀 예측값 반환
- 사용자 정의 스코어링 모델

## 4. 실무에서 주의할 점

TabPy를 쓰면 유연성은 커지지만, 운영 복잡도도 같이 커집니다.

- 외부 Python 서버를 별도로 운영해야 합니다.
- TabPy가 내려가면 관련 계산이 모두 실패할 수 있습니다.
- 계산은 시각화 맥락과 파티셔닝 설정에 영향을 받습니다.
- 같은 통합 문서를 공유받은 사람도 연결 환경을 다시 갖춰야 할 수 있습니다.

실무에서는 다음 기준으로 판단하는 편이 안전합니다.

- Tableau 기본 함수로 가능한가?
- LOD나 테이블 계산으로 대체 가능한가?
- 운영 환경에서 Python 서버를 안정적으로 관리할 수 있는가?

즉, TabPy는 강력하지만 “무조건 Python으로 넘기기”보다 `정말 Tableau 기본 기능으로 해결이 안 될 때` 선택하는 것이 유지보수 측면에서 더 좋습니다.
