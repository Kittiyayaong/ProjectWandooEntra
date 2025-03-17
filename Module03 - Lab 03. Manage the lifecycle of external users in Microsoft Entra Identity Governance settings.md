# Module 03 - Implement Access Management for Apps
## 03. Manage the lifecycle of external users in Microsoft Entra Identity Governance settings

### Lab 설명 
1. Lifecycle workflows(수명 주기 워크플로)?
Microsoft Entra ID Governance의 Lifecycle Workflows는 조직이 Microsoft Entra 사용자를 관리하는 데 도움을 주는 새로운 ID 거버넌스 기능입니다. 이 기능은 사용자의 라이프사이클 동안 자동으로 실행되는 특정 프로세스를 포함합니다1.

2. 주요 프로세스 
* 가입자: 개인이 액세스가 필요한 범위에 입장할 때. 예를 들어 회사나 조직에 새로 입사한 신입 사원을 들 수 있습니다.
* 이동자: 개인이 조직 내 경계 사이를 이동할 때. 이 이동에는 더 많은 액세스 또는 권한이 필요할 수 있습니다. 마케팅에 있던 사용자가 현재 영업 조직의 멤버가 된 경우를 예로 들 수 있습니다.
* 탈퇴자: 개인이 액세스가 필요한 범위를 떠날 때. 이 움직임에는 액세스 권한 삭제가 필요할 수 있습니다. 예를 들어 퇴직한 직원 또는 해고된 직원이 있습니다.

3. 목적
* 자동화된 작업: Lifecycle Workflows는 사용자가 라이프사이클을 통해 이동할 때 자동으로 실행되는 특정 작업을 포함합니다. 예를 들어, 새로운 직원의 고용 날짜 7일 전에 관리자에게 이메일을 보내는 작업이 있습니다1.
* 중앙 집중식 관리: 모든 워크플로우를 한 곳에서 쉽게 생성하고 관리할 수 있습니다.
* 문제 해결 및 감사: 워크플로우 히스토리와 감사 로그를 통해 문제를 쉽게 해결하고, 감사 및 규정 준수를 지원합니다

### 시나리오 
액세스 패키지 요청이 승인되어 디렉토리에 초대된 외부 사용자가 더 이상 액세스 패키지 할당을 받지 못할 때 발생하는 일을 선택할 수 있습니다. 이는 사용자가 모든 액세스 패키지 할당을 포기하거나 마지막 액세스 패키지 할당이 만료되는 경우에 발생할 수 있습니다. 기본적으로 외부 사용자가 더 이상 액세스 패키지 할당을 받지 못하면 디렉토리에 로그인할 수 없습니다. 30일이 지나면 해당 사용자의 게스트 사용자 계정이 디렉토리에서 제거됩니다.

#### Exercise 1 - Microsoft Entra Identity Governance settings
* Task 1 - Manage the lifecycle of external users in Microsoft Entra Identity Governance settings

1. Entra admin > Identity Governance > Entitlement management > Settings > Edit
![image](https://github.com/user-attachments/assets/895537df-1024-4b01-a357-d3625e1238bf)

2. 설정값
* Block external user from signing in to this directory: yes (외부 사용자가 액세스 패키지에 대한 마지막 할당을 잃었을 때, 이 디렉토리에 로그인하지 못하도록 차단)
* Remove external: yes (외부 사용자가 액세스 패키지에 대한 마지막 할당을 잃게 되면, 이 디렉토리에서 게스트 사용자 계정을 제거)
* Number of days before removing external user from this directory: 0 (게스트 사용자 계정이 액세스 패키지에 대한 마지막 할당을 잃는 즉시 삭제하려면 이 디렉토리에서 외부 사용자를 제거하기 며칠 전의 날짜를 0으로 설정합니다.)

3. 설정 완료 
