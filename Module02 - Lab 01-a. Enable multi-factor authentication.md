# Module 02 - Implement an Authentication and Access Management Solution
## 01. Enable multi-factor authentication

### 시나리오 
조직의 보안을 개선하기 위해 Microsoft Entra ID에 대한 다중 인증을 활성화가 필요합니다. 

#### Exercise 1 - Review and enable Multi-factor Authentication in Azure
* Task 1 - Review Azure Multi-Factor Authentication options
   
1. https://entra.microsoft.com (Entra Console)로 로그인
2. Entra.microsoft.com > Protection > Multifactor authentication > 중앙에 configure(Additional cloud-based multifactor authentication settings) 클릭 >

![image](https://github.com/user-attachments/assets/40949181-692f-4d8c-8e4f-069eeb18430a)
   
4. 새 브라우저 페이지에서 Azure 사용자 및 서비스 설정에 대한 MFA 옵션을 확인할 수 있습니다.

![image](https://github.com/user-attachments/assets/4d277a30-0ace-4bc7-a33b-907de778a5c8)

여기에서 지원되는 인증 방법을 선택할 수 있습니다. 위 화면에서 모든 인증 방법이 선택됩니다. 앱 비밀번호를 활성화하거나 비활성화할 수도 있으며, 이를 통해 사용자는 다중 인증을 지원하지 않는 앱의 고유 계정 비밀번호를 만들 수 있습니다. 이 기능을 통해 사용자는 해당 앱에 고유한 다른 비밀번호를 사용하여 Microsoft Entra 신원으로 인증할 수 있습니다.

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
