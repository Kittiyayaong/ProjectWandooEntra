# Module 02 - Implement an Authentication and Access Management Solution
## 04. Identity protection (Enable sign in and user risk policies)

### Lab 설명
1. Identity Protection 
Microsoft Entra의 Identity Protection은 머신 러닝 기반 위험 감지를 통해 사용자 로그인 및 사용자 자체를 분석하고, 위험이 탐지되었을 때 자동으로 조치를 취하도록 구성할 수 있는 보안 기능입니다. 사용자 위험(User Risk)과 로그인 위험(Sign-in Risk)을 기준으로 조건부 액세스를 설정하여 위협에 선제 대응할 수 있습니다.

> ⭐️ Tips. 관련 링크
[ID protection](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id-protection)

---

## ✅ Exercise 1 - Enable User risk policy

---
* Task 1 - Configure the policy
  
User risk policy란?

Microsoft Entra ID Protection의 User Risk Policy는 조직이 사용자 계정의 위험을 평가하고 이에 대한 적절한 조치를 취할 수 있도록 돕는 중요한 보안 기능입니다. 이 정책은 사용자 계정이 잠재적으로 위험에 처했을 때 이를 탐지하고, 조사하며, 완화하는 과정을 포함합니다.

---

1. Entra admin > Protection > Identity Protection > user risk policy로 이동

   <img width="1439" alt="스크린샷 2025-06-24 오후 12 45 35" src="https://github.com/user-attachments/assets/3c945baa-bd64-4635-b8bb-afd7babe3989" />

2. 설정값
   * Assignment: Wandoo-user1
   * User risk: High
   * Control: Allow access > Require password change
   * Policy Enforcement: Enabled
  
  <img width="949" alt="스크린샷 2025-06-24 오후 12 46 52" src="https://github.com/user-attachments/assets/fae2f441-4781-4762-aff5-63173e832105" />

3. 설정 완료

---

* Task 2 - Enable Sign-in risk policy

> ⭐️ Tips. sign-in risk policy
> Microsoft Entra ID Protection의 Sign-in Risk Policy는 사용자의 로그인 활동을 모니터링하고, 의심스러운 활동이 감지되면 이에 대한 적절한 조치를 취하는 중요한 보안 기능입니다. 이 정책은 사용자가 로그인할 때 발생할 수 있는 다양한 위험 요소를 평가하고, 이를 통해 보안 위협을 최소화합니다.

---

1. task 1과 동일한 위치에서 'sign-in risk policy'로 이동
2. 사용자 위험 정책과 마찬가지로 로그인 위험 정책도 사용자와 그룹에게 할당할 수 있으며, 사용자를 정책에서 제외할 수 있습니다.
3. Sign-in risk: High
4. Control: Allow access > Require multifactor authentication
5. Policy Enforcement: Enabled
6. 설정 완료 
