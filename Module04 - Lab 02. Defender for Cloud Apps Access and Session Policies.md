# 작성중 -- 진행하지 마시오 

# Module 04 - Implement Access Management for Apps
## 02. Defender for Cloud Apps Access and Session Policies

### 시나리오 
Microsoft Defender for Cloud Apps를 사용하면 모니터링 중인 클라우드 앱에 특화된 추가 조건부 액세스 정책을 만들 수 있습니다. 이러한 정책은 Microsoft Defender for Cloud Apps 포털의 제어 메뉴에서 만들 수 있습니다.

#### Exercise 1 - Create and test the Conditional Access App Contol policy
* Task 1 - Configure Microsoft Entra ID to work with Defender for Cloud Apps

1. https://entra.microsoft.com > Protection > Conditional Access > + Create new policy
2. policy name: Wandoo Monitor
3. User: wandoo-user1 account
4. target resources: none
5. Select 'Select apps', choose Office 265, and select Select.
![image](https://github.com/user-attachments/assets/fc5ee664-8954-4501-bab9-85d0f0d22434)

7. Under Access controls, select Session and 0 controls selected.
8. Select the Use Conditional Access App Control box, leave the default of Monitor only, and select Select.
![image](https://github.com/user-attachments/assets/6df6bd5b-57ca-4906-9464-68aa14b9ca3b)

9. Under Enable policy, select On, and select Create.

#### Exercise 2 - Setup alerts in Microsoft Defender for Cloud Apps
* Task 1 - Access Microsoft Defender for Cloud Apps and create Conditional Access App Control

애플리케이션을 등록하면 앱과 Microsoft ID 플랫폼 간에 Trust 관계가 형성됩니다. trust는 단방향으로 앱은 Microsoft ID 플랫폼을 신뢰하지만 그 반대의 경우는 아닙니다.

1. Security.microsoft.com > Cloud apps > policies > Policy management > Create policy > Access policy 
![image](https://github.com/user-attachments/assets/30f2b596-25c0-474d-8eca-91f69e7a1be4)

2. 
