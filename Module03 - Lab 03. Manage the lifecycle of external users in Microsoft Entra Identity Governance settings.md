# Wandoo-KT 에서는 제외합니다. 

# Module 03 - Implement Access Management for Apps
## 03. Manage the lifecycle of external users in Microsoft Entra Identity Governance settings

### Lab 설명 
1. 외부 사용자의 수명 주기 관리

액세스 패키지 요청을 통해 디렉터리에 초대된 외부 사용자에게 할당된 액세스 패키지가 더 이상 없는 경우에 수행할 작업을 선택할 수 있습니다. 사용자가 모든 액세스 패키지 할당을 포기하거나 마지막 액세스 패키지 할당이 만료되는 경우 이 상황이 발생할 수 있습니다. 기본적으로 외부 사용자에게 더 이상 액세스 패키지 할당이 없는 경우 디렉터리에 로그인하지 못하도록 차단됩니다. 30일 후에는 해당 게스트 사용자 계정이 디렉터리에서 제거됩니다. 외부 사용자가 로그인 또는 삭제에서 차단되지 않거나 외부 사용자가 로그인에서 차단되지 않고 삭제되도록 구성할 수도 있습니다.

#### Exercise 1 - Microsoft Entra Identity Governance settings
* Task 1 - Manage the lifecycle of external users in Microsoft Entra Identity Governance settings

1. Entra admin > Identity Governance > Entitlement management > Settings > Edit
![image](https://github.com/user-attachments/assets/895537df-1024-4b01-a357-d3625e1238bf)

2. 설정값
* Block external user from signing in to this directory: yes (외부 사용자가 액세스 패키지에 대한 마지막 할당을 잃었을 때, 이 디렉토리에 로그인하지 못하도록 차단)
* Remove external: yes (외부 사용자가 액세스 패키지에 대한 마지막 할당을 잃게 되면, 이 디렉토리에서 게스트 사용자 계정을 제거)
* Number of days before removing external user from this directory: 0 (게스트 사용자 계정이 액세스 패키지에 대한 마지막 할당을 잃는 즉시 삭제하려면 이 디렉토리에서 외부 사용자를 제거하기 며칠 전의 날짜를 0으로 설정합니다.)

3. 설정 완료 
