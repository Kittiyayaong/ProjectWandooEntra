# Module 01 - Implement an Identity Management Solution 
## 03. Add guest users to the directory 

### 시나리오 
고객사A 많은 공급업체와 협력하고 있으며, 해당 공급업체의 계정을 사내 디렉토리에 게스트로 추가가 필요합니다. 

#### Microsoft Entra External ID
- 외부 사용자를 조직 리소스에 안전하게 초대하고 관리할 수 있도록 지원
- B2B(비즈니스 간) 협업을 위해 설계
- 조직 외부 사용자(예: 파트너, 공급업체, 프리랜서 등)를 Entra ID 테넌트에 "게스트"로 초대 가능

## Exercise 1 - Add guest users to the directory

* Task - Add the guest user

1. https://entra.microsoft.com > Identity > users > All users > New user > invite external user 

---

Tips.참고 - 그룹 이메일 주소는 지원되지 않습니다. 개인의 이메일 주소를 입력하세요. 또한 일부 이메일 제공업체는 사용자가 받은 편지함 필터링과 같은 작업을 돕기 위해 이메일 주소에 더하기 기호(+)와 추가 텍스트를 추가할 수 있도록 허용합니다. 그러나 Microsoft Entra ID는 현재 이메일 주소에서 더하기 기호를 지원하지 않습니다. 배달 문제를 방지하려면 더하기 기호와 @ 기호까지 이어지는 문자를 생략하세요.

---

3. 개인 메일 주소 작성 ex) soyoungdemo@outlook.com
4. user type: Guest
5. Review 후 invite 선택으로 설정 완료

#### Exercise 2 - Invite guest users in bulk
* Task 1 - Bulk user invite (다수의 게스트 초대)

1. https://entra.microsoft.com > Identity > users > All users > 우측 상단에 Bulk operaton > bult invite

![image](https://github.com/user-attachments/assets/07fd023a-3cbd-4264-bdbc-ec5de85037d0)

2. 벌크 초대 사용자 창에서 초대 속성이 있는 샘플 CSV 템플릿에 다운로드를 선택합니다.
3. 편집기를 사용하여 CSV 파일을 확인하고 템플릿을 검토합니다.
4. .csv 템플릿을 열고 각 게스트 사용자에게 줄을 추가합니다. 필요한 값은 다음과 같습니다:

![image](https://github.com/user-attachments/assets/b940387c-939c-4e48-aef8-3235ce518ca8)

* 초대할 이메일 주소 - 초대를 받을 사용자
* 리디렉션 URL - 초대받은 사용자가 초대를 수락한 후 전달되는 URL입니다.

5. 파일 저장
6. bult invite user 화면에서 .csv 파일 업로드

![image](https://github.com/user-attachments/assets/d476ed4e-66e7-4004-8dac-6b623ab8552f)

7. 파일이 검증을 통과하면 제출을 선택하여 초대장을 추가하는 Azure 대량 작업이 시작 됨
8. 설정 완료 
