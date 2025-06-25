# Module 02 - Implement an Authentication and Access Management Solution
## 02. Configure and deploy self-service password reset

### 시나리오 
조직의 사용자들이 IT 지원 없이 스스로 비밀번호를 재설정(Self-Service Password Reset, SSPR) 할 수 있도록 설정하는 방법을 익힙니다.


## ✅  Exercise 1 - Create a group with SSPR(Self-Service Password Reset) enabled and add users to it
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

---

* Task 2 - Enable SSPR for you test group

1. Entra admin center > Identity > Protection > Password reset > Self sevice password reset enabled (Selected로 설정) 
2. Select group에 Task 1에서 만든 그룹 할당 (Wandoo-SSPR) 후 save

   <img width="1440" alt="image" src="https://github.com/user-attachments/assets/e99075ba-7da0-4ad5-a05f-f6ed75eb3858" />

3. Entra admin center > Identity > Protection > Password reset > **Authentication method** 클릭
4. 이 디렉토리의 사용자가 비밀번호를 재설정하기 위해 필요한 대체 식별 방법의 수를 정의합니다.

  <img width="1552" alt="스크린샷 2025-06-24 오후 12 37 46 2" src="https://github.com/user-attachments/assets/91f588bc-bcf4-42bc-9c58-3a43b08f9c7d" />


> ⭐️ Tips. SSPR 인증 방법 설정값
> 
| 항목                                      | 설명                                                                                                                                                                                                                             |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Number of methods required to reset** | 사용자가 비밀번호를 재설정할 때 필요한 인증 방법 수를 설정합니다. 현재는 **2개**로 설정되어 있음. 보안 강화를 위해 권장됩니다.                                                                                                                                                    |
| **Methods available to users**          | 사용자가 선택할 수 있는 인증 방법 중 활성화된 항목. <br>현재는 `Security questions`는 **비활성화** 상태이며, <br>기타 인증 방법(e.g. 전화, 인증 앱 등)은 [auth methods policy](https://entra.microsoft.com/#view/Microsoft_AAD_IAM/AuthenticationMethodsMenuBlade)에서 별도 관리됨. |
| **알림 메시지**                              | - 이 설정은 조직의 일반 사용자에게만 적용됩니다. <br>- **관리자는 항상 SSPR이 활성화되며**, 반드시 2개의 인증 방법을 등록해야 비밀번호 재설정이 가능함.                                                                                                                                |

> ⭐️ Tips. 권장 설정
> 
| 설정 항목   | 권장 값                         |
| ------- | ---------------------------- |
| 인증 수단 수 | 2개                           |
| 보안 질문   | 사용 안 함 (대신 인증 앱, 전화번호 사용 권장) |

7. 설정 완료 

### 🔗 [다음 Lab으로 이동하기 »](https://github.com/Kittiyayaong/ProjectWandooEntra/blob/main/Module02%20-%20Lab%2004.%20Identity%20protection.md)
