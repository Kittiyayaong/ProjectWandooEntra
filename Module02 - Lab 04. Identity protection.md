# Module 02 - Implement an Authentication and Access Management Solution
## 04. Identity protection (Enable sign in and user risk policies)

### Lab 설명
1. Identity Protection
Microsoft Entra ID Protection은 조직이 ID 기반 위험을 검색, 조사 및 수정하는 데 도움이 됩니다. 이러한 위험을 조건부 액세스와 같은 도구로 전달하여 액세스 결정을 내리거나 추가 조사 및 상관 관계를 위해 SIEM(보안 정보 및 이벤트 관리) 도구로 전송할 수 있습니다.

2. 주요 기능 및 목적
* 위험 탐지: Microsoft Entra ID Protection은 매일 수조 개의 신호를 분석하여 익명 IP 주소 사용, 비밀번호 스프레이 공격, 유출된 자격 증명 등과 같은 위험 행동을 탐지합니다
* 위험 조사: 탐지된 모든 위험은 보고서에 기록되며, 관리자는 이를 통해 위험을 조사하고 조치를 취할 수 있습니다. 주요 보고서에는 위험 탐지, 위험한 로그인, 위험한 사용자가 포함됩니다
* 위험 완화: 위험 기반 조건부 액세스 정책을 통해 사용자가 강력한 인증 방법을 제공하거나 다중 인증을 수행하거나 안전한 비밀번호 재설정을 수행하도록 요구할 수 있습니다. 사용자가 이러한 액세스 제어를 성공적으로 완료하면 위험이 자동으로 완화됩니다

3. 관련 링크
[ID protection](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id-protection)

#### Exercise 1 - Enable User risk policy

---
* Task 1 - Configure the policy
  
User risk policy란?

Microsoft Entra ID Protection의 User Risk Policy는 조직이 사용자 계정의 위험을 평가하고 이에 대한 적절한 조치를 취할 수 있도록 돕는 중요한 보안 기능입니다. 이 정책은 사용자 계정이 잠재적으로 위험에 처했을 때 이를 탐지하고, 조사하며, 완화하는 과정을 포함합니다.

---

1. Entra admin > Protection > Identity Protection > user risk policy로 이동
2. 설정값
   * Assignment: Wandoo-user1
   * User risk: High
   * Control: Allow access > Require password change
   * Policy Enforcement: Enabled
3. 설정 완료

---
* Task 2 - Enable Sign-in risk policy

sign-in risk policy

Microsoft Entra ID Protection의 Sign-in Risk Policy는 사용자의 로그인 활동을 모니터링하고, 의심스러운 활동이 감지되면 이에 대한 적절한 조치를 취하는 중요한 보안 기능입니다. 이 정책은 사용자가 로그인할 때 발생할 수 있는 다양한 위험 요소를 평가하고, 이를 통해 보안 위협을 최소화합니다.

---

1. task 1과 동일한 위치에서 'sign-in risk policy'로 이동
2. 사용자 위험 정책과 마찬가지로 로그인 위험 정책도 사용자와 그룹에게 할당할 수 있으며, 사용자를 정책에서 제외할 수 있습니다.
3. Sign-in risk: High
4. Control: Allow access > Require multifactor authentication
5. Policy Enforcement: Enabled
6. 설정 완료 
