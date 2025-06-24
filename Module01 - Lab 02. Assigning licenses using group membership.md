# Module 01 - Implement an Identity Management Solution 
## 02. Assigning licenses using group membership

### 🔍 실습 목표
Microsoft Entra ID 내 **보안 그룹**, **Microsoft 365 그룹**, 그리고 **동적 그룹(Dynamic Group)** 을 생성하고, 사용자 라이선스를 그룹 기반으로 관리하는 방법을 학습합니다.

### ✅ 실습에서 배울 내용 요약

| 항목                        | 설명                                                                 |
|---------------------------|----------------------------------------------------------------------|
| **Security Group**        | 리소스 접근 제어 및 라이선스 부여 목적. Assigned 멤버 방식 사용                      |
| **Microsoft 365 Group**   | Teams, Outlook 등 협업 도구와 통합. 협업 기능 중심 그룹                              |
| **Dynamic Group**         | 사용자 속성 기반 자동 멤버 구성. 유지 관리 자동화 가능                              |
| **Role-Assignable 설정**  | Security Group에 Microsoft Entra 역할 할당 가능 여부 설정 (한 번 설정 후 변경 불가)      |
| **Membership Type**       | Assigned (수동 지정) 또는 Dynamic (조건 기반 자동 지정)                            |

---
#### Exercise 1 - Create a security group and add a user
* Task: Create a security group in Microsoft Entra ID
##### 목적  
보안 그룹을 생성하고, 사용자에게 라이선스 할당 준비

##### Step
1. Browse to https://entra.microsoft.com.
2. Identity > Goups > All Goups > New group
 
   <img width="817" alt="스크린샷 2025-06-24 오전 9 56 15" src="https://github.com/user-attachments/assets/2c70f684-a9a9-4606-a36f-30c5b20f68e9" />

3. Create a group using the following information:

   | 항목                          | 값                                         |
   |-----------------------------|--------------------------------------------|
   | Group type                  | Security                                   |
   | Group name                  | IT Lab Administrators                      |
   | Description                 | Administrators that manage the IT Lab      |
   | Microsoft Entra roles 설정 | **No** (역할 할당 불가 그룹으로 설정)       |
   | Membership type             | Assigned                                   |
   | Member                      | `Wandoo-user1` 추가                        |


  <img width="704" alt="image" src="https://github.com/user-attachments/assets/8efac9eb-1c42-45ab-8a61-8dee4b29d5c4" />


5. Select the Create button

> ✅ **Tips** 역할 할당 가능 그룹이란?

- **Yes 선택 시**: 해당 그룹은 Microsoft Entra 역할을 할당할 수 있는 **역할 할당 가능 그룹**이 됨
- **주의**: 이 설정은 생성 후 변경 불가
- 라이선스나 리소스 제어 용도의 그룹은 "No"로 설정해야 안전

| 항목                        | 일반 그룹       | 역할 할당 가능 그룹  |
|---------------------------|----------------|---------------------|
| Microsoft Entra 역할 할당 | ❌ 불가         | ✅ 가능               |
| 보안 정책                 | 일반 정책       | 강화된 정책 적용       |
| 설정 변경 가능 여부       | 대부분 가능      | ❌ 변경 불가 (역할 설정) |

---

#### Exercise 2 - Create a Microsoft 365 group in Microsoft Entra ID
* Task: Create the group

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

