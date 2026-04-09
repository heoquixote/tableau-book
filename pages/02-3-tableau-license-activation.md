## 학습 목표

- Tableau Cloud 계정을 생성하고 인증할 수 있습니다.
- Tableau Desktop을 Tableau Cloud 기반으로 활성화할 수 있습니다.
- 활성화 완료 여부를 직접 확인할 수 있습니다.

## 목차

1. Tableau 라이선스 활성화

## 1. Tableau 라이선스 활성화

### 1-1. 태블로 인증 과정

Tableau를 사용하려면 단순히 프로그램만 설치하는 것으로 끝나지 않습니다. 계정 생성, 클라우드 접속, 추가 인증, 라이선스 활성화까지 하나의 흐름으로 이해해야 실제 실습 환경을 안정적으로 구성할 수 있습니다.

![태블로 인증 과정 이미지 삽입 예정](../assets/01-3-tableau-auth-flow.png)

이 과정을 익숙한 게임 로그인 흐름에 비유하면 다음과 같이 이해할 수 있습니다.

| 메이플스토리 | Tableau |
| --- | --- |
| 1. 넥슨 ID 로그인: 게임을 시작하려면 계정이 필요함 | 1. Tableau.com 계정 생성: Tableau Desktop이나 Tableau Cloud를 사용하려면 계정이 필요함 |
| 2. 서버 선택: 원하는 서버에 접속 | 2. Teamsparta Cloud 로그인: 팀스파르타에서 사용하는 Tableau Cloud에 접속 |
| 3. 2차 인증: OTP나 보안카드로 본인 확인 | 3. Auth 인증: Salesforce Authenticator, Google Authenticator 등으로 본인 확인 |
| 4. 캐릭터 접속 완료 | 4. Tableau 사용 시작: Desktop 사용, 대시보드 게시, 협업 기능 활용 |

이 비유의 핵심은 Tableau도 기업 환경에서는 단순 실행형 프로그램이 아니라, 계정과 권한, 보안 인증을 포함한 서비스형 도구라는 점입니다.

### 1-2. Tableau Cloud 계정 이메일 활성화

처음 Tableau Cloud를 사용하려면 초대 메일을 통해 계정을 활성화해야 합니다.

1. 이메일에서 `You've Been Invited to Tableau Cloud` 메일을 확인합니다.  
   안내 메일이 오지 않았다면 태블로 서버/클라우드 담당자에게 문의합니다.

![Cloud 초대 메일 이미지 삽입 예정](../assets/01-3-cloud-invite-email.png)

2. 메일 안의 `Join Now` 버튼을 클릭합니다.

![Join Now 버튼 이미지 삽입 예정](../assets/01-3-cloud-join-now.png)

3. 이름과 비밀번호를 설정합니다.

![이름과 비밀번호 설정 이미지 삽입 예정](../assets/01-3-cloud-set-profile.png)

![추가 설정 화면 이미지 삽입 예정](../assets/01-3-cloud-set-password.png)

4. 설정이 완료되면 Tableau Cloud 로그인 화면으로 이동합니다.

![Cloud 로그인 완료 화면 이미지 삽입 예정](../assets/01-3-cloud-login-finish.png)

이 단계가 끝나면 Tableau Cloud 계정 자체는 활성화된 상태가 됩니다. 다만 조직 정책에 따라 추가 인증 수단 등록이 필요할 수 있습니다.

### 1-3. 추가 인증 방법 등록

조직 보안 정책에 따라 첫 로그인 시 추가 인증(MFA) 설정이 필요할 수 있습니다. 대표적으로 Salesforce Authenticator 또는 Google Authenticator 기반 인증을 사용합니다.

#### 1. Salesforce Authenticator로 인증하는 경우

추가 인증 수단 등록 화면에서 `Salesforce Authenticator`를 선택합니다.

![추가 인증 수단 선택 이미지 삽입 예정](../assets/01-3-auth-method-select.png)

![Salesforce Authenticator 선택 화면 이미지 삽입 예정](../assets/01-3-salesforce-auth-select.png)

설정 절차는 다음과 같습니다.

1. 휴대폰에 Salesforce Authenticator 앱을 설치합니다.

- Google Play: [Salesforce Authenticator](https://play.google.com/store/apps/details?id=com.salesforce.authenticator)
- App Store: [Salesforce Authenticator](https://apps.apple.com/us/app/salesforce-authenticator/id782057975)

2. 스마트폰에서 앱을 실행합니다.

![Salesforce Authenticator 설치 이미지 삽입 예정](../assets/01-3-salesforce-auth-install.png)

3. `Add an Account` 또는 `계정 추가`를 눌러 계정을 추가합니다.

![Salesforce Authenticator 계정 추가 이미지 삽입 예정](../assets/01-3-salesforce-auth-add-account.png)

4. 앱 화면에 표시된 두 단어를 PC 인증창에 입력합니다.

![Salesforce Authenticator 단어 인증 이미지 삽입 예정](../assets/01-3-salesforce-auth-words.png)

5. 앱에서 갱신되는 확인 코드를 PC 화면에 입력합니다.

6. 확인 코드와 검증 도구 이름을 설정하면 등록이 완료됩니다.

![Salesforce Authenticator 등록 완료 이미지 삽입 예정](../assets/01-3-auth-finish.png)

#### 2. Google Authenticator로 인증하는 경우

추가 인증 수단 등록 화면에서 `일회용 암호 생성기`를 선택합니다.

![일회용 암호 생성기 선택 이미지 삽입 예정](../assets/01-3-google-auth-select.png)

설정 절차는 다음과 같습니다.

1. 휴대폰에 Google Authenticator 앱을 설치합니다.

- Google Play: [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=ko&gl=US&pli=1)
- App Store: [Google Authenticator](https://apps.apple.com/us/app/google-authenticator/id388497605)

2. 앱을 실행하고 코드 추가를 선택합니다.

![Google Authenticator 설치 이미지 삽입 예정](../assets/01-3-google-auth-install.png)

![Google Authenticator 코드 추가 이미지 삽입 예정](../assets/01-3-google-auth-add-code.png)

3. `QR 코드 스캔`을 눌러 PC에 표시된 QR 코드를 등록합니다.

![Google Authenticator QR 등록 이미지 삽입 예정](../assets/01-3-google-auth-qr.png)

4. 앱에 표시되는 일회용 코드를 PC 화면에 입력합니다.

![Google Authenticator 확인 코드 이미지 삽입 예정](../assets/01-3-google-auth-code.png)

5. 확인 코드와 검증 도구 이름을 설정하면 등록이 완료됩니다.

![Google Authenticator 등록 완료 이미지 삽입 예정](../assets/01-3-auth-finish.png)

### 1-4. Tableau Desktop 라이선스 활성화

Tableau Desktop 설치가 끝났다면 이제 조직에서 제공받은 라이선스로 활성화합니다.

1. Tableau 활성화 화면에서 `서버에 로그인하여 활성화`를 선택합니다.

![서버 로그인 활성화 이미지 삽입 예정](../assets/01-3-desktop-activate-server.png)

2. Tableau Cloud를 선택합니다.

![Tableau Cloud 선택 이미지 삽입 예정](../assets/01-3-desktop-select-cloud.png)

3. Tableau Cloud에 사용할 사용자 이름을 입력합니다.  
   이때 앞 단계에서 활성화한 Tableau Cloud 이메일을 입력합니다.

![Cloud 사용자 이름 입력 이미지 삽입 예정](../assets/01-3-desktop-cloud-username.png)

4. URL 입력창이 나오면 `teamsparta`를 입력합니다.  
   표시되지 않으면 건너뜁니다.

![Site URL 입력 이미지 삽입 예정](../assets/01-3-desktop-site-url.png)

5. 이메일과 비밀번호를 입력합니다.

![이메일과 비밀번호 입력 이미지 삽입 예정](../assets/01-3-desktop-email-password.png)

6. Authenticator 인증을 진행합니다.

![Authenticator 인증 화면 이미지 삽입 예정](../assets/01-3-desktop-authenticator.png)

7. 활성화 프로세스 완료 화면이 나타나면 `계속`을 눌러 마칩니다.

![활성화 완료 화면 이미지 삽입 예정](../assets/01-3-desktop-activation-finish.png)

### 1-5. 활성화 확인 방법

정상적으로 활성화되었는지 확인하려면 Tableau Desktop 내부에서 제품 키 상태를 확인하면 됩니다.

1. Tableau Desktop 상단 메뉴에서 `도움말 > 제품 키 관리`를 클릭합니다.

![제품 키 관리 메뉴 이미지 삽입 예정](../assets/01-3-desktop-manage-product-key.png)

2. Creator 제품 키가 보이면 정상적으로 활성화된 것입니다.

![Creator 제품 키 확인 이미지 삽입 예정](../assets/01-3-desktop-product-key-check.png)
