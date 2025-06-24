# Module 02 - Implement an Authentication and Access Management Solution
## 01-b. Configure MFA to be required for login

### 시나리오 
사용자 계정에 대한 MFA를 구성하는 방법을 살펴보겠습니다. 이 방법은 특정 사용자에게만 수동으로 MFA를 설정할 수 있어 테스트 용도로 적합하지만, 대규모 환경에는 비효율적입니다.

#### Exercise 2 - Configure MFA to be required for login
* Task 1 - Configure Microsoft Entra Per-User MFA

1. Entra admin center > users > all users > 우측 점 3개 클릭 (...) > per-user MFA 선택 
![image](https://github.com/user-attachments/assets/bf58be4f-18ec-4df1-b8cf-d6c5c4aee77b)

2. 새로운 브라우저 탭/창이 열리고 다중 인증 사용자 설정 대화 상자가 열립니다. 사용자를 선택한 다음 오른쪽의 빠른 단계를 사용하여 사용자별로 MFA를 활성화하거나 비활성화할 수 있습니다.
   
![image](https://github.com/user-attachments/assets/e0119b4f-9f2b-469a-ba84-1aa3352e2217)

4. 설정 대상인 user 클릭 후 enable MFA 클릭 > 팝업 enable 클릭
5. 설정 완료

### 🔗 [다음 Lab으로 이동하기 »](https://github.com/Kittiyayaong/ProjectWandooEntra/blob/main/Module02%20-%20Lab%2002.%20Configure%20and%20deploy%20self-service%20password%20reset.md)
