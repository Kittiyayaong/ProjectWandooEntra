# Module 03 - Implement Access Management for Apps
## 01. Defender for Cloud Apps application discovery and enforcing restrictions

### 시나리오 
Microsoft Defender for Cloud Apps는 네트워크 트래픽의 로그를 사용하여 사용자가 액세스하는 애플리케이션을 식별합니다. 온프레미스 방화벽의 트래픽 로그는 가장 일반적인 애플리케이션과 이러한 앱에 액세스하는 사용자에 대한 스냅샷 보고서를 제공합니다. 관리되는 장치의 트래픽은 Microsoft Defender for Cloud Apps 검색 개요 대시보드에 입력됩니다

#### Exercise 1 - Defender for Cloud Apps discovery
* Task 1 - Discovery apps in Defender for Cloud Apps

1. https://security.microsoft.com/ > Cloud apps > Cloud app catalog > Browse by category에 Cloud Storage 검색 후 클릭 > Dropbox 찾아서 우측 (...) 클릭 > Sanctioned 클릭 > next  
![image](https://github.com/user-attachments/assets/f0347d78-24d6-4899-b18e-a4052b780e72)

Tips. Sanctioned 앱은 조직 내에서 공식적으로 승인된 애플리케이션을 의미합니다. 이러한 앱은 안전하다고 간주되며, 사용이 허용됩니다. 반면, unsanctioned 앱은 승인되지 않은 애플리케이션으로, 사용이 제한되거나 금지될 수 있습니다

* Task 2 - Restrict Apps in Defender for Cloud Apps
![image](https://github.com/user-attachments/assets/c714e9d5-ebf2-467d-8a6a-525551125de6)

우측에 동그라미 표시 클릭으로 바로 'unsanctioned' 처리가 가능

Tips. 애플리케이션과 해당 애플리케이션을 실행 및 취소할 때 지연이 발생합니다. 최대 5분까지 기다려야 할 수도 있습니다.

Tips. 애플리케이션이 승인되지 않은 상태로 차단되면 브라우저, 비공개 브라우저 또는 클라우드 앱용 Microsoft Defender와 통합된 MDE(Microsoft Defender for Endpoint)에 온보딩된 클라이언트의 스토어 다운로드를 통해 애플리케이션에 액세스할 수 없습니다.
