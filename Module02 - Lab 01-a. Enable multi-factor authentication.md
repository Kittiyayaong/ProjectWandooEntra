# Module 02 - Implement an Authentication and Access Management Solution
## 01-a. Enable multi-factor authentication

### 시나리오 
조직의 보안을 개선하기 위해 Microsoft Entra ID에 대한 MFA 활성화가 필요합니다. 

| 개념 | 설명 |
|------|------|
| **MFA (Multi-Factor Authentication)** | 사용자 인증 시, 비밀번호 외 추가 요소(예: 전화, 앱, OTP 등)를 요구해 보안을 강화하는 기술 |
| **Azure MFA** | Microsoft Entra ID에서 제공하는 MFA 기능. 사용자가 앱, 전화, 하드웨어 토큰 등을 이용하여 인증 가능 |
| **Conditional Access** | 특정 조건(사용자, 위치, 디바이스 등)에 따라 MFA 또는 앱 차단 등 보안 정책을 유연하게 적용하는 기능 |
| **App Passwords** | MFA를 지원하지 않는 앱에 대해 별도 비밀번호를 생성하여 로그인 가능하게 해주는 기능 (보안 리스크가 있어 가급적 사용 제한 권장) |

### Lab 실습 요약

| Exercise | 목표 | 요약 |
|----------|------|------|
| **Exercise 1** | Azure MFA 옵션 확인 | MFA 설정 페이지에서 인증 방식 및 옵션(App password 포함) 검토 |
| **Exercise 2** | 조건부 액세스 정책 생성 | 특정 사용자(Wandoo-user1)가 특정 앱(Office 365)에 접근 시 MFA 요구하도록 설정 |

---

## ✅ Exercise 1 - Review and enable Multi-factor Authentication in Azure
* Task 1 - Review Azure Multi-Factor Authentication options
   
1. https://entra.microsoft.com (Entra Console)로 로그인
2. Entra.microsoft.com > Protection > Multifactor authentication > 중앙에 configure(Additional cloud-based multifactor authentication settings) 클릭 

   ![image](https://github.com/user-attachments/assets/40949181-692f-4d8c-8e4f-069eeb18430a)
   
3. 새 브라우저 페이지에서 Azure 사용자 및 서비스 설정에 대한 MFA 옵션을 확인할 수 있습니다.

   <img width="1552" alt="image" src="https://github.com/user-attachments/assets/5f921b94-066c-440b-8a55-759dea1efc2c" />

> ⭐️ Tips. Per-user Multifactor Authentication 설정
> 
| 기능 항목                           | 주요 목적               | 왜 필요한가?           |
| ------------------------------- | ------------------- | ----------------- |
| App Password                    | MFA 미지원 앱에 로그인 허용   | 유연성 제공, 업무 연속성 확보 |
| Trusted IPs                     | 내부망에서 MFA 생략        | UX 개선 + 보안 균형     |
| Verification Options            | 인증 방식 제한            | 보안 수준 제어          |
| Remember MFA on trusted devices | 자주 쓰는 디바이스에서는 인증 생략 | 반복 인증 피로도 감소      |

> 
> App passwords: MFA를 지원하지 않는 애플리케이션에서 계정 인증을 가능하게 하기 위해 생성하는 고유 비밀번호입니다.
> * **Allow users to create app passwords to sign in to non-browser apps**
> * 사용자가 MFA를 지원하지 않는 앱(예: IMAP 이메일 클라이언트 등)에 로그인할 수 있도록 App Password(앱 비밀번호)를 생성할 수 있도록 허용합니다.
> * **Do not allow users to create app passwords to sign in to non-browser apps**
> * 사용자가 App Password를 생성하지 못하도록 제한합니다. 보안 강화를 위해 이 옵션 선택을 권장합니다.

> Trusted IPs:  기능은 특정 네트워크에서 로그인할 때 MFA를 우회하도록 설정하여 사용자 경험을 향상시킬 수 있습니다.
>
> - **Skip multifactor authentication for requests from federated users on my intranet**
>  - 사내 네트워크(인트라넷)에서 연합된 사용자의 MFA를 생략합니다.
> - **Skip multifactor authentication for requests from following range of IP address subnets**
>  - 지정된 IP 대역에서 발생한 로그인 요청에 대해 MFA 생략을 허용합니다.
>  - IP 주소 입력 예: `203.0.113.0/24`

> Verification options
>
> - MFA 인증 방법 설정은 현재 **Authentication methods policy**를 통해 관리됩니다.
> - 관련 설정은 [authentication methods policy](https://entra.microsoft.com/#view/Microsoft_AAD_IAM/AuthenticationMethodsPolicyBlade/~/Methods) 링크를 통해 변경할 수 있습니다.

> Remember multifactor authentication on trusted device
> 
> - **Allow users to remember multifactor authentication on devices they trust (between one to 365 days)**
>   - 신뢰하는 디바이스에서는 MFA를 일정 기간 동안 생략할 수 있습니다.
>   - 사용자가 MFA를 생략할 수 있는 일수 설정: `7`일 (기본값)
  
> ⚠️ 권장: Conditional Access의 "sign-in frequency" 정책을 함께 설정해 신뢰 디바이스/로케이션에서의 세션 수명을 연장하세요.  
> 특히 'Remember MFA on a trusted device' 사용 시, 지속 기간을 최소 90일 이상으로 설정하는 것이 좋습니다.

자세한 내용: [Learn more about reauthentication prompts](https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-session-lifetime)

----------

* Task 2 - Setup conditional access rules for MFA 

다음으로 네트워크의 특정 앱에 액세스하는 게스트 사용자에게 MFA를 적용하는 조건부 액세스 정책 규칙을 설정하는 방법을 살펴보겠습니다.

1. Entra admin center(Entra.microsoft.com) > Identity > Protection > conditional Access > New policy > Create new policy
![image](https://github.com/user-attachments/assets/f87054fd-929b-4b4b-b942-91d1511b96d1)

2. 설정값
   * Name: Wandoo MFA Conditional Access
   * User: wandoo-user1
   * Target Resource: Resource(Cloud apps) > Select resources > select > office 365 선택
   * Network: configure: yes > Any network or location
   * Access control: Grant access > Require multifactor authentication / 하단에 require all the selected controls
   * enable policy
   * create로 설정 완료
     
3. 이제 선택한 사용자와 애플리케이션에 대해 MFA가 활성화되었습니다. 다음에 게스트가 해당 앱에 로그인하려고 할 때 MFA에 등록하라는 메시지가 표시됩니다.
