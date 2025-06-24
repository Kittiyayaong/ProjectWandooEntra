# Module 03 - Implement Access Management for Apps
## 05. Configure Privileged Identity Management for Microsoft Entra roles

### Lab 설명 

1. PIM(Privileged Identity Managemend) 
Privileged Identity Management(PIM)는 관리자 권한을 "항상 보유"하지 않고, 필요할 때만 활성화할 수 있도록 도와주는 보안 서비스입니다.  

> ⭐️ 이 실습을 통해 다음을 학습합니다:
> - **임시 권한할당**(Eligible roles) vs **영구 권한할당**(Permanent assignment)
> - PIM 설정: 승인, MFA, 만료, 알림, 검토
> - PIM의 주요 이점: 보안 강화, 권한 오남용 감소, 감사용 로그 확보

---

## ✅  Exercise 1 - Configure Microsoft Entra role settings
* Task 1 - Open role settings

1. Entra admin > Identity governance > Privileged identity Management > Microsoft Entra roles > Setting

   <img width="1181" alt="스크린샷 2025-06-24 오후 2 02 21" src="https://github.com/user-attachments/assets/e9bd9b6b-bc83-4584-9f29-d9b10c931d89" />

2. 'Compliance Administrator' 클릭 후 해당 role에 대해서 확인

  <img width="1188" alt="스크린샷 2025-06-24 오후 2 02 49" src="https://github.com/user-attachments/assets/160d2a24-6d52-47ac-94e6-e78ba8f48502" />

---

* Task 2 - Require approval to activate

여러 승인자를 설정하는 경우, 승인은 여러명 중 한 명이 승인 또는 거부하는 즉시 완료됩니다. 복수 승인자 모두의 동의가 필요한 구조는 불가능하므로, “A와 B 둘 다 승인해야 최종 승인” 같은 방식은 지원하지 않습니다. 

1. Task 1에서 클릭한 role의 왼쪽 상단 edit 클릭

  ![image](https://github.com/user-attachments/assets/9d4a7570-09eb-4e28-8174-47ffb655f8c7)

2. Require approval to activate 체크박스 클릭
3. approvers 클릭

  ![image](https://github.com/user-attachments/assets/284ed035-9a81-4aa5-ba22-881d0a791194)
  
4. update 클릭 후 설정완료

---

## ✅ Exercise 2 - Use PIM to assign Microsoft Entra roles
* Task 1 - Assign a role

Microsoft Entra ID를 사용하면 글로벌 관리자가 영구적인 Microsoft Entra 관리자 역할 할당을 할 수 있습니다. 이러한 역할 할당은 Microsoft Entra 관리자 센터, Azure 포털 또는 PowerShell 명령을 사용하여 만들 수 있습니다.

권한 부여 신원 관리(PIM) 서비스를 통해 권한 부여 역할 관리자는 영구적인 관리자 역할 할당을 할 수 있습니다. 또한 권한 부여 역할 관리자는 사용자에게 Microsoft Entra 관리자 역할을 부여할 수 있습니다. 자격이 있는 관리자는 역할이 필요할 때 해당 역할을 활성화한 다음 권한이 완료되면 만료될 수 있습니다.

1. Entra admin > Identity governance > Privileged identity Management > Microsoft Entra roles > Roles 클릭 ? Add assignents

   ![image](https://github.com/user-attachments/assets/eb205255-33da-442d-b359-7ee73cc7697b)

2. 'Compliance Administrator' 검색 추 클릭 > next

  ![image](https://github.com/user-attachments/assets/087b79f8-84c0-4cfd-bb84-2f2a1d8fabfd)

4. Eligible assigment로 클릭 후 설정 완료 
