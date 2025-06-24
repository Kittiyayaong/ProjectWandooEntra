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
   
   <img width="1342" alt="스크린샷 2025-06-24 오전 9 36 16" src="https://github.com/user-attachments/assets/46176751-311e-48f9-8560-0c9889918beb" />
   <img width="1133" alt="스크린샷 2025-06-24 오전 9 36 40" src="https://github.com/user-attachments/assets/f5fc3c90-9c82-42f9-a3db-29c4eb3260c1" />
   <img width="801" alt="스크린샷 2025-06-24 오전 9 36 52" src="https://github.com/user-attachments/assets/5ceb3e38-1f6f-4d2c-8f37-d974c396f416" />

2. 'Application administrator' role 확인 후 설정
![image](https://github.com/user-attachments/assets/5880cbcd-8a0d-42af-8cf3-40fe90e9b23c)

> ✅ **Tips**: 전체 역할은 (공식 문서)[https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference]에서 확인할 수 있으며, 100개 이상의 역할이 존재합니다.  
>
> 대표적인 Entra의 built-in role
> 
| 역할                                | 설명                                                                             |
| --------------------------------- | ------------------------------------------------------------------------------ |
| **Global Administrator**          | 전체 권한. 가급적 최소 인원만 사용                                                            |
| **User Administrator**            | 사용자 및 그룹 생성/수정 권한                                                                 |
| **Application Administrator**     | 애플리케이션 등록 및 API 권한 관리                                                              |
| **Groups Administrator**          | 그룹 생성 및 관리 권한<br>(Access Package 설정 시 필수 역할 중 하나)                               |
| **Privileged Role Administrator** | 다른 관리자 역할을 할당/회수할 수 있는 권한<br>(PIM 설정 및 역할 할당 승인 기능 포함)              |
| **Security Reader**               | 보안 이벤트 열람, Microsoft Defender 및 Entra 로그 리포트 보기 가능                                     |
| **Billing Administrator**         | 라이선스, 구독, 과금 관련 설정 및 인보이스 확인 가능                                                  |
| **Authentication Administrator**  | MFA 정책, 패스워드 리셋, 인증 방법 정책 설정 권한<br>(조건부 액세스 일부 포함)                          |

3. Active > Assignment type

> ✅ **Tips** Assignment type (할당 유형)
> 역할을 *어떻게* 할당할 것인지 결정하는 옵션입니다:
> 
| 옵션 | 설명 |
|------|------|
| **Eligible (적격)** | 사용자가 항상 역할을 갖는 것이 아니라, 필요할 때 **활성화 요청**을 해야 사용할 수 있는 상태. Privileged Identity Management(PIM)의 기본 모델입니다. |
| **Active (활성)** | 역할이 **즉시 활성화**되며, 별도 요청 없이 **지속적으로 사용 가능**합니다. 보안보다는 편의성이 우선되는 경우 사용됩니다. |

---

> ✅ **Tips** Permanently assigned (영구 할당)
> 
| 옵션 | 설명 |
|------|------|
| ✅ 체크 시 | 역할이 **기한 없이 무기한**으로 부여됩니다. 종료일 없이 계속 유지됩니다. |
| ⬜ 체크 해제 시 | 아래 `Assignment starts` / `Assignment ends`에서 역할의 시작일과 종료일을 수동으로 지정해야 합니다. |

---
> ✅ **Tips** Maximum allowed assignment duration is permanent

- 이 문구는 **해당 역할이 영구 할당을 허용하도록 정책이 설정**되어 있음을 의미합니다.
- 만약 영구 할당이 **허용되지 않는 역할 또는 테넌트 정책**이라면, 최대 할당 기간이 표시됩니다 (예: 30일, 1년 등).

---

> ✅ **Tips** 예시 시나리오

- **Assignment type**: Active  
- **Permanently assigned**: ✅  
- → 이 설정은 **즉시 활성화되고, 무기한 유지되는 역할 할당**을 의미합니다.

- **Assignment type**: Eligible  
- **Permanently assigned**: ⬜ (기간 지정)  
- → 이 설정은 **요청 시에만 활성화되며, 제한된 기간 동안만 유지되는 권한**입니다.

---

> 📌 참고: 보안 원칙에 따라 **가능하면 Eligible + 기간 제한** 방식이 권장되며, Global Administrator 등 고위험 역할은 최소 인원만 Active로 유지해야 합니다.

5. Assign
   
   <img width="571" alt="스크린샷 2025-06-24 오전 9 45 16" src="https://github.com/user-attachments/assets/a51c81cd-16ea-4fc8-a643-790b7174db32" />

6. 설정 완료
 
  <img width="1385" alt="스크린샷 2025-06-24 오전 9 50 17" src="https://github.com/user-attachments/assets/52e5a81d-bdad-4bc3-b58c-f5e7168427dd" />


### 🔗 [다음 Lab으로 이동하기 »](https://github.com/Kittiyayaong/ProjectWandooEntra/blob/main/Module01%20-%20Lab%2002.%20Assigning%20licenses%20using%20group%20membership.md)
