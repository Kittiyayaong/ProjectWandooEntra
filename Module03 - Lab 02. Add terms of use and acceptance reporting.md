# Module 03 - Implement Access Management for Apps
## 02. Add terms of use and acceptance reporting

### 시나리오 
Microsoft Entra 이용 약관 정책은 조직이 최종 사용자에게 정보를 제공하는 데 사용할 수 있는 간단한 방법을 제공합니다. 이 프레젠테이션을 통해 사용자는 법적 또는 규정 준수 요구 사항에 대한 관련 고지 사항을 확인할 수 있습니다. 이 문서에서는 이용 약관(ToU) 정책을 시작하는 방법을 설명합니다.

#### Exercise 1 - Set up a Term of Use and test them
* Task 1 - Add terms of use (참고 - Azure 포털에서 사용할 이용 약관입니다.)

1. Entra admin > Identity Governance > Entitlement Management > temrs of use > New terms
![image](https://github.com/user-attachments/assets/6ad6a2d5-75ca-4527-ba6e-a45e211ac8cc)

2. 설정값
![image](https://github.com/user-attachments/assets/09a073d1-e860-4ba6-a354-7b3900de0959)

   * Name: Wandoo terms
   * Terms file: pdf 확장자의 terms 파일 첨부
   * Default Language: Eng
   * Display name: wandoo terms
   * Require users to expand the terms of use: On (최종 사용자가 이용 약관을 수락하기 전에 이용 약관을 확인)
   * Require users to consent on every device: Off (최종 사용자가 액세스하는 모든 디바이스에서 사용 약관을 수락하도록 요구하려면 사용자가 모든 디바이스에 동의하도록 설정/ 활성화 시 추가 app 설치 필요할 수 있음) 
   * Expire consents: On (일정에 대한 사용약관동의 만료)
3. 설정 완료
