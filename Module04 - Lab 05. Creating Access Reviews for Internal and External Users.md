# Module 04 - Implement Access Management for Apps
## 05. Creating Access Reviews for Internal and External Users

### 시나리오 
권한 있는 사용자 액세스도 비슷한 방식으로 정기적으로 검토해야 합니다. 이러한 권한 할당은 고가 액세스 할당이므로 회사에서 확인한 대로 일관된 기준으로 검토해야 합니다. 사용되지 않거나 불필요한 권한 할당은 제거해야 합니다. 또한 회사에 더 이상 근무하지 않거나 회사 내 부서를 변경한 사용자에 대해서도 자동 제거를 구성해야 합니다.

#### Exercise 1 - Create an internal Access review
* Task - Create a new Access review

1. Entra Admin > Identity Governance > Access revice > New access review
2. 설정값
![image](https://github.com/user-attachments/assets/b912623c-da96-49d4-a177-26a59310c157)

   * Select what to review: Terms + Groups
   * Review Scope: All Microsoft 365 groups with guest users
   * Scope: Guest users only
   * Reviewer: 다음 단계는 검토자를 결정하는 것입니다. 이러한 검토자는 자체 검토를 수행하는 회원이 될 수도 있고, 부서 전체에 대한 접근 권한을 검토하는 경우 감독관에게 할당될 수도 있습니다. 또한 검토자가 해당 권한 접근 권한을 회원에서 자동으로 제거하도록 응답하지 않을 때 작업을 설정할 수도 있습니다.
  3. 설정완료
