# Module 03 - Implement Access Management for Apps
## 04. Creating Access Reviews for Internal and External Users

### Lab 설명 

1. Access REview란? 

Microsoft Entra의 일부인 Microsoft Entra ID의 액세스 검토를 통해 조직은 그룹 멤버 자격, 엔터프라이즈 애플리케이션에 대한 액세스 및 역할 할당을 효율적으로 관리할 수 있습니다. 적절한 사용자만 계속 액세스할 수 있도록 사용자의 액세스를 정기적으로 검토할 수 있습니다.



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
