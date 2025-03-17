# Module 02 - Implement an Authentication and Access Management Solution
## 05. Configure an Multifactor authentication registration policy

### 시나리오 
멀티팩터 인증은 사용자 이름과 비밀번호 이상의 사용자를 확인할 수 있는 수단을 제공합니다. 이는 사용자 로그인에 두 번째 보안 계층을 제공합니다. 사용자가 MFA 프롬프트에 응답하려면 먼저 Microsoft Entra 멀티팩터 인증에 등록해야 합니다. 모든 사용자에게 할당되도록 Microsoft Entra 조직의 MFA 등록 정책을 구성해야 합니다.

#### Exercise 1 - Set up MFA registration policy
* Task 1 - Policy configuration

![image](https://github.com/user-attachments/assets/1760c9df-0933-46e4-8b30-31a4d8aebfd8)


1. Entra admin > Protection > Identity protection > Multifactor authentication registration policy
2. User: 모든 사용자 또는 개인 및 그룹 선택에서 롤아웃을 제한하는 경우 선택할 수 있습니다.또한 사용자를 정책에서 제외하도록 선택할 수도 있습니다.
3. Control: 제어에서 Microsoft Entra ID 멀티팩터 인증 등록 필요가 선택되었으며 변경할 수 없음을 확인합니다.


