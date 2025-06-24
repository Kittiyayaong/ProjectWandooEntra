# Module 01 - Implement an Identity Management Solution 
## 02. Assigning licenses using group membership

### 🔍 실습 목표
Microsoft Entra ID 내 **보안 그룹**, **Microsoft 365 그룹**, 그리고 **동적 그룹(Dynamic Group)** 을 생성하고, 사용자 라이선스를 그룹 기반으로 관리하는 방법을 학습합니다.

### ✅ Exercise 요약

| 항목                | Exercise 1         | Exercise 2          | Exercise 3             |
| ----------------- | ------------------ | ------------------- | ---------------------- |
| 그룹 유형             | Security Group     | Microsoft 365 Group | Dynamic Security Group |
| 주요 목적             | 라이선스 및 리소스 권한 관리   | Teams/Outlook 협업    | 조건 기반 자동 사용자 구성        |
| 멤버십 방식            | Assigned (수동)      | Assigned (수동)       | Dynamic (자동)           |
| 역할 할당 가능 여부 설정 포함 | 포함됨 (Yes/No 선택 가능) | 해당 없음               | 해당 없음                  |

---

### 그룹 유형별 차이점 - Microsoft Entra ID 기준

#### ✅ 그룹 유형 개요

| 그룹 유형                  | 주요 사용 목적                     | 특징 및 실제 활용 방식 |
|---------------------------|------------------------------------|----------------------|
| **Security Group**        | 권한 제어 / 라이선스 관리          | - 앱/리소스 접근 권한 제어<br>- Intune 정책 대상 지정<br>- 라이선스 할당<br>- Azure RBAC 할당 가능 |
| **Microsoft 365 Group**   | 협업 (Teams, Outlook 등)           | - Teams, Planner, SharePoint, Outlook 등 자동 연결<br>- 협업 공간 자동 생성 |
| **Dynamic Group**         | 조건 기반 사용자 자동 분류         | - user.department, jobTitle 등 조건 설정<br>- 사용자 자동 포함/제외<br>- HR 시스템 연동 자동화 가능 |

---

#### 🚩 직관적 차이 예시

| 예시 | 그룹 유형 | 이유 |
|------|-----------|------|
| 영업팀 직원 모두에게 라이선스 자동 부여 | Dynamic + Security Group | 부서 속성 기반 자동 할당 (Dynamic) + 라이선스 가능 (Security) |
| 마케팅팀의 Teams 협업 채널 구성 | Microsoft 365 Group | Teams, SharePoint, Outlook 등 협업 도구 자동 연결 |
| 개발자 전용 Azure 리소스 접근 제어 | Security Group | 보안 정책과 역할 기반 권한(RBAC) 적용에 최적 |

---

#### 🔍 왜 구분할까?

- **Microsoft 365 Group**: 협업에 최적화 (M365 앱들과 연결됨)
- **Security Group**: IT 정책, 앱, 자원 접근 제어에 활용
- **Dynamic Group**: 조건 기반 자동 구성으로 관리 효율화

---

> 🔄 실제 운영에서는 이 3가지 그룹 유형을 목적에 맞게 **조합하여 사용하는 것이 일반적**입니다.
> 예: 동적 보안 그룹(Dynamic Security Group)으로 자동 분류 + 해당 그룹에 정책 및 라이선스 적용

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
  <img width="1115" alt="스크린샷 2025-06-24 오전 9 57 23" src="https://github.com/user-attachments/assets/c4d9febb-5c23-45f2-9209-996da7366d22" />


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
  
##### 목적  
협업 플랫폼과 통합 가능한 Microsoft 365 그룹 생성

##### Step
1. Browse to https://entra.microsoft.com.
2. Identity > select Groups > All Groups > New group.
3. Create a group using the following information

   | 항목              | 값                  |
   |------------------|---------------------|
   | Group type       | Microsoft 365       |
   | Group name       | Wandoo Sales     |
   | Membership type  | Assigned            |
   | Member           | `Wandoo-user1` 추가  |

<img width="1185" alt="스크린샷 2025-06-24 오전 10 17 54" src="https://github.com/user-attachments/assets/22392495-77f9-401a-a098-e584825f5805" />


4. When complete, verify the group named Wandoo sales is shown in the All groups list.

---

#### Exercise 3 - Create a Microsoft 365 group in Microsoft Entra ID
* Task 1 : Create the dynamic group

디렉토리를 표준화했기 때문에 이제 동적 그룹을 활용할 수 있습니다. 동적 그룹을 생성하여 프로덕션에서 동적 그룹을 만들 준비가 되었는지 확인해야 합니다.

#### 목적  
조건 기반 자동 사용자 그룹 구성

#### Step

1. Sign in to the https://entra.microsoft.com with an provided administrator account. You need at least User Administrator role in the tenant.
2. Select Identity > Groups > All groups > New group.

   | 항목              | 값                         |
   |------------------|----------------------------|
   | Group type       | Security                   |
   | Group name       | Wandoo-dynamic             |
   | Membership type  | **Dynamic user**           |
   | Owner            | `Wandoo-user1` 지정         |

![image](https://github.com/user-attachments/assets/42036b82-6b8d-4cee-863e-d2c494ac0576)

4. 규칙 구문 상자 오른쪽 위에서 편집을 선택합니다. 규칙 구문 편집 창에서 규칙 구문 상자에 다음 식을 입력합니다:

user.objectId -ne null

![image](https://github.com/user-attachments/assets/b0c9f755-9e7e-4d25-b1ce-db16c8ffaacb)

5. save 후 create로 설정 완료 

* Task 2. Verify the members have been added
  
1. Entra console > Identity > Goups > All group > Wandoo-dynamic 클릭 > Member로 이동
2. Wandoo-user1 선택 후 완료 

![image](https://github.com/user-attachments/assets/5ddb4de6-eefd-4c4b-a69e-6f61531ce8c6)

