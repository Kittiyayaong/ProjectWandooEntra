# Module 01 - Implement an Identity Management Solution 
## 03. Add guest users to the directory 

### Microsoft Entra External ID
- 외부 사용자를 조직 리소스에 안전하게 초대하고 관리할 수 있도록 지원
- B2B(비즈니스 간) 협업을 위해 설계
- 조직 외부 사용자(예: 파트너, 공급업체, 프리랜서 등)를 Entra ID 테넌트에 "게스트"로 초대 가능

### Exercise Summary - Lab 03: Add Guest Users

| Exercise 번호 | 주요 작업 내용                              | 입력 값/작업 방식                          | 결과 및 기대 효과 |
|---------------|----------------------------------------------|--------------------------------------------|------------------|
| **Exercise 1** | 외부 사용자(게스트) 개별 초대                  | - Email 주소 (예: soyoungdemo@outlook.com) <br> - User type: Guest | 해당 사용자가 테넌트에 "게스트 사용자"로 등록됨 |
| **Exercise 2** | 게스트 사용자 대량 초대 (CSV 업로드)           | - 템플릿 `.csv` 다운로드 및 작성 <br> - Email, Redirect URL 포함 | 다수의 게스트 사용자를 한 번에 초대 가능 |


## ✅ Exercise 1 - Add guest users to the directory

* Task - Add the guest user

1. https://entra.microsoft.com > Identity > users > All users > New user > invite external user 
 
  ![Uploading 스크린샷 2025-06-24 오전 10.52.06.png…]()

---

>  ⭐️ Tips. 게스트 사용자 초대 시에는 **+기호 없이**, **그룹 메일이 아닌 개인 메일 주소**만 입력해야 합니다.
| 구분 | 설명 |
|------|------|
| ❌ **그룹 이메일 주소는 사용 불가** | 예: `team@company.com`, `support@company.com` 같은 다수 사용자에게 전달되는 그룹 메일은 초대할 수 없음 |
| ❌ **이메일 주소에 "+" 기호는 사용 불가** | 예: `soyoung+test@outlook.com` 은 **Microsoft Entra ID에서는 지원하지 않음** |
| ✅ **반드시 실제 개인 이메일 주소 사용** | 예: `soyoungdemo@outlook.com` 같이 명확한 1인 이메일 주소만 사용해야 함 |

---

2. 개인 메일 주소 작성 ex) soyoungdemo@outlook.com

  <img width="895" alt="스크린샷 2025-06-24 오전 10 52 52" src="https://github.com/user-attachments/assets/8f37bb4c-4ff9-43d6-8580-bddb278a8d6c" />
 
4. Property로 이동하여 **user type: Guest** 기입

  <img width="675" alt="스크린샷 2025-06-24 오전 10 53 00" src="https://github.com/user-attachments/assets/f81a4b51-4f14-4c90-b4bc-e28340a4c657" />

6. Review 후 invite 선택으로 설정 완료

  <img width="1172" alt="image" src="https://github.com/user-attachments/assets/7c0cc06c-bb99-41a5-a182-c51ce94dc550" />

>  ⭐️ Tips. 초대한 external guest가 받는 메일

   <img width="827" alt="스크린샷 2025-06-24 오전 11 33 52" src="https://github.com/user-attachments/assets/5373572d-7349-4690-9cc1-d47f6927e99e" />

---

## ✅ Exercise 2 - Invite guest users in bulk
* Task 1 - Bulk user invite (다수의 게스트 초대)

1. https://entra.microsoft.com > Identity > users > All users > 우측 상단에 Bulk operaton > bult invite

 ![image](https://github.com/user-attachments/assets/07fd023a-3cbd-4264-bdbc-ec5de85037d0)

2. **Bulk invite users**에서 csv template를 다운로드 한 후, 샘플 게정을 추가하여 저장합니다. 

 <img width="1222" alt="스크린샷 2025-06-24 오전 11 50 58" src="https://github.com/user-attachments/assets/ce2d5b3e-b864-4103-8145-d5668d1eb7e1" />

* 초대할 이메일 주소 - 초대를 받을 사용자
* 리디렉션 URL - 초대받은 사용자가 초대를 수락한 후 전달되는 URL입니다.

3. 파일 저장
4. bult invite user 화면에서 .csv 파일 업로드한 후, 파일이 검증을 통과하면 제출을 선택하여 초대장을 추가하는 Azure 대량 작업이 시작

   <img width="274" alt="스크린샷 2025-06-24 오전 11 51 24" src="https://github.com/user-attachments/assets/afd4da1e-4a4c-4092-a617-5931ec7fcf1f" />

5. 설정 완료 
