# Module 03 - Implement Access Management for Apps
## 05. Configure Privileged Identity Management for Microsoft Entra roles

### 시나리오 
권한 있는 역할 관리자는 적격 역할 할당을 활성화하는 사용자의 경험을 변경하는 등 Microsoft Entra 조직에서 권한 있는 신원 관리(PIM)를 사용자 지정할 수 있습니다. PIM 구성에 익숙해야 합니다.

#### Exercise 1 - Configure Microsoft Entra role settings
* Task 1 - Open role settings

1. Entra admin > Identity governance > Privileged identity Management > Microsoft Entra roles > Setting
2. 'Compliance Administrator' 클릭 후 해당 role에 대해서 확인

* Task 2 - Require approval to activate

여러 승인자를 설정하는 경우, 승인은 그 중 한 명이 승인 또는 거부하는 즉시 완료됩니다. 최소 두 명의 사용자에게 승인을 요구할 수 없습니다. 역할을 활성화하기 위해 승인을 요구하려면 다음 단계를 따릅니다.

1. Task 1에서 클릭한 role의 왼쪽 상단 edit 클릭
![image](https://github.com/user-attachments/assets/9d4a7570-09eb-4e28-8174-47ffb655f8c7)
2. Require approval to activate 체크박스 클릭
3. approvers 클릭
![image](https://github.com/user-attachments/assets/284ed035-9a81-4aa5-ba22-881d0a791194)
4. update 클릭 후 설정완료

#### Exercise 2 - Use PIM to assign Microsoft Entra roles
* Task 1 - Assign a role

Microsoft Entra ID를 사용하면 글로벌 관리자가 영구적인 Microsoft Entra 관리자 역할 할당을 할 수 있습니다. 이러한 역할 할당은 Microsoft Entra 관리자 센터, Azure 포털 또는 PowerShell 명령을 사용하여 만들 수 있습니다.

권한 부여 신원 관리(PIM) 서비스를 통해 권한 부여 역할 관리자는 영구적인 관리자 역할 할당을 할 수 있습니다. 또한 권한 부여 역할 관리자는 사용자에게 Microsoft Entra 관리자 역할을 부여할 수 있습니다. 자격이 있는 관리자는 역할이 필요할 때 해당 역할을 활성화한 다음 권한이 완료되면 만료될 수 있습니다.

1. Entra admin > Identity governance > Privileged identity Management > Microsoft Entra roles > Roles 클릭 ? Add assignents
![image](https://github.com/user-attachments/assets/eb205255-33da-442d-b359-7ee73cc7697b)

2. 'Compliance Administrator' 검색 추 클릭 > next
![image](https://github.com/user-attachments/assets/087b79f8-84c0-4cfd-bb84-2f2a1d8fabfd)

3. Eligible assigment로 클릭 후 설정 완료 
