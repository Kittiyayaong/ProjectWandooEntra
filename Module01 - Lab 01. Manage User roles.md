# Module 01 - Implement an Identity Management Solution 
## 01. Manage User Roles 

### 시나리오 
최근 애플리케이션 관리자로 업무를 수행할 새로운 직원을 채용했습니다. 새 사용자를 생성하고 적절한 역할을 할당해야 합니다.

#### Exercise 1 - Create a new user and test their application admin right
* Task 1 - Add a new user
   
1. https://entra.microsoft.com (Entra Console)로 로그인
2. Identity > User > All User > + New user > Create New user
   
![image](https://github.com/user-attachments/assets/c982bf07-e1f3-4d71-ac28-c9fdeebfc688)

3. Mark the Auto-generate password option.

* Task 2 - Assign a role to a user
  
Microsoft Entra ID를 사용하면 권한이 적은 역할로 ID 작업을 관리할 수 있는 제한된 관리자를 지정할 수 있습니다. 관리자는 사용자 추가 또는 변경, 관리 역할 할당, 사용자 비밀번호 재설정, 사용자 라이선스 관리, 도메인 이름 관리 등의 목적으로 할당될 수 있습니다.

1. Entra console > Identity > User > All users > 리스트에서 생성한 Wandoo-user 1 > Add assignments 클릭
3. Application administrator role 추가 
4. Select the Next button.
5. Mark the Active value for Assignment Type.
6. Select Assign
   
![image](https://github.com/user-attachments/assets/dbedb034-7888-4ab8-88ad-2b3fb5491d9a)

7. 저장 후 완료 
