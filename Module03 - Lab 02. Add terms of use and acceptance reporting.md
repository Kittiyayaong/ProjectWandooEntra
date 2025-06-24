# Module 03 - Implement Access Management for Apps
## 02. Add terms of use and acceptance reporting

### Lab 설명
Microsoft Entra에서 **Terms of Use(ToU)** 정책을 설정하고, 사용자 동의 상태를 추적하는 방법을 익힙니다. 이는 **법적 고지, 보안 정책 동의, 규정 준수 목적**으로 사용됩니다.

> ⭐️핵심 구성 및 설명
> 
> - **Require users to expand**: 사용자가 동의 전에 내용을 반드시 펼쳐서 확인하도록 강제
> - **Require users to consent on every device**: 디바이스별 동의 필요 설정
> - **Expire consents / Duration before re-acceptance**: 일정 주기마다 재동의 유도
> - **CA 정책과 연동**: ToU 정책은 반드시 Conditional Access 정책을 통해 활성화되어야 적용됨

---

## ✅ Exercise 1 - Set up a Term of Use and test them
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

### 🔗 [다음 Lab으로 이동하기 »](https://github.com/Kittiyayaong/ProjectWandooEntra/blob/main/Module03%20-%20Lab%2004.%20Creating%20Access%20Reviews%20for%20Internal%20and%20External%20Users.md)
