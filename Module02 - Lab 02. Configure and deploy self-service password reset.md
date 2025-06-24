# Module 02 - Implement an Authentication and Access Management Solution
## 02. Configure and deploy self-service password reset

### 시나리오 
조직의 사용자들이 IT 지원 없이 스스로 비밀번호를 재설정(Self-Service Password Reset, SSPR) 할 수 있도록 설정하는 방법을 익힙니다.


#### Exercise 1 - Create a group with SSPR(Self-Service Password Reset) enabled and add users to it
* Task 1 - Create a group to assign SSPR

SSPR 구성이 예상대로 작동하는지 확인하려면 먼저 제한된 사용자 집합에 SSPR을 롤아웃해야 합니다. 제한된 롤아웃을 위한 보안 그룹을 만들고 그룹에 사용자를 추가해 보겠습니다.

1. Entra admin center > Identity > Groups > all groups > New Group 생성
2. 설정값

| 항목                                       | 값                                             |
|------------------------------------------|------------------------------------------------|
| **Group type**                            | Security                                       |
| **Group name**                            | Wandoo-SSPR                                    |
| **Group description**                     | SSPR(Self-Service Password Reset) group        |
| **Microsoft Entra roles assignable**      | No                                             |
| **Membership type**                       | Assigned                                       |
| **Owners**                                | No owners selected                             |
| **Members**                               | 1 member selected (Adele Vance)                |

  <img width="681" alt="스크린샷 2025-06-24 오후 12 32 04" src="https://github.com/user-attachments/assets/59052552-6b4e-4303-b106-babf8855f107" />
  <img width="1184" alt="스크린샷 2025-06-24 오후 12 31 58" src="https://github.com/user-attachments/assets/f50c7c02-cf1e-4ea4-b78d-a67b9b019cda" />

3. SSPR용 그룹 Create
  <img width="1173" alt="image" src="https://github.com/user-attachments/assets/e11c0dbc-9fe6-4e4c-90c5-66037bf1fe72" />


* Task 2 - Enable SSPR for you test group

1. Entra admin center > Identity > Protection > Password reset > Self sevice password reset enabled (Selected로 설정) 
2. Select group에 Task 1에서 만든 그룹 할당 (Wandoo-SSPR) 후 save

   <img width="1440" alt="image" src="https://github.com/user-attachments/assets/e99075ba-7da0-4ad5-a05f-f6ed75eb3858" />

3. Entra admin center > Identity > Protection > Password reset > **Authentication method** 클릭
5. 이 디렉토리의 사용자가 비밀번호를 재설정하기 위해 필요한 대체 식별 방법의 수를 정의합니다. 설정은 2로 진행합니다. 

![image](https://github.com/user-attachments/assets/a98feb01-6bdd-4891-8f10-d5b303b04fed)

7. 설정 완료 

### 🔗 [다음 Lab으로 이동하기 »]()
