# Module 01 - Implement an Authentication and Access Management Solution
## 01. Manage user roles

### 시나리오 
고객사A는 최근 애플리케이션 관리자로 업무를 수행할 새로운 직원을 채용했습니다. 새 사용자를 생성하고 적절한 역할을 할당해야 합니다.

#### Exercise 1 - Create a new user and test their application admin rights
* Task 1 - Add a new user
  
1. https://entra.microsoft.com > Identity > Users > All Users > New User > Create new user.
2. 설정값 
![image](https://github.com/user-attachments/assets/c452610b-e4ac-4d73-b0fe-862e7cfb8301)

3. 비밀번호 자동 생성 옵션(Auto-generate password)을 체크
4. 생성 완료

#### Exercise 2 - Assign the application admin role and create an app
* Task 1 - Assign a role to a user
Microsoft Entra ID를 사용하면 권한이 적은 역할로 ID 작업을 관리할 수 있는 제한된 관리자를 지정할 수 있습니다. 관리자는 사용자 추가 또는 변경, 관리 역할 할당, 사용자 비밀번호 재설정, 사용자 라이선스 관리, 도메인 이름 관리 등의 목적으로 할당될 수 있습니다.

1. https://entra.microsoft.com > Identity > Users > All Users > Task 1번에서 생성한 user 클릭 > Assigned roles 클릭
2. 'Application administrator' role 확인 후 설정
![image](https://github.com/user-attachments/assets/5880cbcd-8a0d-42af-8cf3-40fe90e9b23c)

3. Active > Assignment type
4. Assign
5. 설정 완료 
