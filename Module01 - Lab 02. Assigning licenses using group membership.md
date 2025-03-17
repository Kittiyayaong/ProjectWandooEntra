# Module 01 - Implement an Identity Management Solution 
## 02. Assigning licenses using group membership

### 시나리오 
조직에서 Microsoft Entra ID의 보안 그룹을 사용하여 라이선스를 관리하기로 결정했습니다. 새 보안 그룹을 구성하고 해당 그룹에 라이선스를 할당하고 그룹 회원 라이선스가 업데이트되었는지 확인해야 합니다.

#### Exercise 1 - Create a security group and add a user
* Task: Create a security group in Microsoft Entra ID

1. Browse to https://entra.microsoft.com.
2. Identity > Goups > ALl Goups > New group
3. Create a group using the following information:

![image](https://github.com/user-attachments/assets/4f0052b6-5c49-4edf-a133-141fed91c9e6)

+ Group type: Security
+ Group name: IT Lab Administrators
+ Group Description: Administrators that manage the IT Lab
+ Membership type: Assigned
+ Member: task1에서 생성한 Wandoo-user1 추가 

4. Select the No members selected text under Members.
5. Select Delia Dennis from the list of users.
6. Select the Select button.

#### Exercise 2 - Create a Microsoft 365 group in Microsoft Entra ID
* Task: Create the group

  Microsoft Entra 관리자로서의 업무 중 하나는 다양한 유형의 그룹을 만드는 것입니다. 조직의 영업 부서를 위해 새로운 Microsoft 365 그룹을 만들어야 합니다.

1. Browse to https://entra.microsoft.com.
2. Identity > select Groups > All Groups > New group.
3. Create a group using the following information

![image](https://github.com/user-attachments/assets/1c64f3ad-f1ea-4d51-a2f8-9b20561f5cd0)

+ Group type: Microsoft 365
+ Group name: Northwest Sales
+ Membership type: Assigned
+ Member: Wandoo-user1 

4. When complete, verify the group named Northwest sales is shown in the All groups list.

#### Exercise 2 - Create a Microsoft 365 group in Microsoft Entra ID
* Task 1 : Create the dynamic group

디렉토리를 표준화했기 때문에 이제 동적 그룹을 활용할 수 있습니다. 동적 그룹을 생성하여 프로덕션에서 동적 그룹을 만들 준비가 되었는지 확인해야 합니다.

1. Sign in to the https://entra.microsoft.com with an provided administrator account. You need at least User Administrator role in the tenant.
2. Select Identity > Groups > All groups > New group.

![image](https://github.com/user-attachments/assets/42036b82-6b8d-4cee-863e-d2c494ac0576)


+ Group type: Security
+ Group name: Wandoo-dynamic
+ Membership type: Dynamic user
+ Owner: Wandoo-user1 

4. 규칙 구문 상자 오른쪽 위에서 편집을 선택합니다. 규칙 구문 편집 창에서 규칙 구문 상자에 다음 식을 입력합니다:

user.objectId -ne null

![image](https://github.com/user-attachments/assets/b0c9f755-9e7e-4d25-b1ce-db16c8ffaacb)

5. save 후 create로 설정 완료 

* Task 2. Verify the members have been added
  
1. Entra console > Identity > Goups > All group > Wandoo-dynamic 클릭 > Member로 이동
2. Wandoo-user1 선택 후 완료 

![image](https://github.com/user-attachments/assets/5ddb4de6-eefd-4c4b-a69e-6f61531ce8c6)

