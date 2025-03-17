# Module 03 - Implement Access Management for Apps
## 02. Defender for Cloud Apps Access and Session Policies

### 시나리오 
Microsoft Defender for Cloud Apps를 사용하면 모니터링 중인 클라우드 앱에 특화된 추가 조건부 액세스 정책을 만들 수 있습니다. 이러한 정책은 Microsoft Defender for Cloud Apps 포털의 제어 메뉴에서 만들 수 있습니다.

#### Exercise 1 - Create and test the Conditional Access App Contol policy
* Task 1 - Configure Microsoft Entra ID to work with Defender for Cloud Apps

1. https://entra.microsoft.com > Protection > Conditional Access > + Create new policy
2. policy name: Wandoo Monitor
3. User: wandoo-user1 account
4. target resources: none
5. Select 'Select apps', choose Microsoft Forms, and select Select.
6. Under Access controls, select Session and 0 controls selected.
7. 조건부 액세스 앱 제어 사용 상자를 선택하고 기본값인 모니터만 남겨두고 선택
8. Under Enable policy, select On, and select Create.

