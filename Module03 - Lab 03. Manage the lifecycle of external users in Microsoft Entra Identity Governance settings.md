# Module 03 - Implement Access Management for Apps
## 03. Manage the lifecycle of external users in Microsoft Entra Identity Governance settings

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
