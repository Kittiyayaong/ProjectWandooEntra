# Module 02 - Implement an Authentication and Access Management Solution
## 04. Identity protection (Enable sign in and user risk policies)

### 시나리오 
보안의 추가 계층으로 Microsoft Entra 조직의 로그인 및 사용자 위험 정책을 활성화하고 구성해야 합니다.

#### Exercise 1 - Enable User risk policy
* Task 1 - Configure the policy

1. Entra admin > Protection > Identity Protection > user risk policy로 이동
2. 설정값
   * Assignment: Wandoo-user1
   * User risk: High
   * Control: Allow access > Require password change
   * Policy Enforcement: Enabled
3. 설정 완료
  

* Task 2 - Enable Sign-in risk policy

1. task 1과 동일한 위치에서 'sign-in risk policy'로 이동
2. 사용자 위험 정책과 마찬가지로 로그인 위험 정책도 사용자와 그룹에게 할당할 수 있으며, 사용자를 정책에서 제외할 수 있습니다.
3. Sign-in risk: High
4. Control: Allow access > Require multifactor authentication
5. Policy Enforcement: Enabled
6. 설정 완료 
