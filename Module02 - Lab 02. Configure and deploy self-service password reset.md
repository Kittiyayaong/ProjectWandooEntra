# Module 02 - Implement an Authentication and Access Management Solution
## 02. Configure and deploy self-service password reset

### 시나리오 
회사는 직원들에게 권한을 부여하고 셀프 서비스 비밀번호 재설정을 활성화하기로 결정했습니다. 조직에서 이 설정을 구성해야 합니다.

#### Exercise 1 - Create a group with SSPR(Self-Service Password Reset) enabled and add users to it
* Task 1 - Create a group to assign SSPR

SSPR 구성이 예상대로 작동하는지 확인하려면 먼저 제한된 사용자 집합에 SSPR을 롤아웃해야 합니다. 제한된 롤아웃을 위한 보안 그룹을 만들고 그룹에 사용자를 추가해 보겠습니다.

1. Entra admin center > Identity > Groups > all groups > New Group
2. 설정
![image](https://github.com/user-attachments/assets/d01535b7-24c3-4de6-bfb7-59c55d6a01fd)

3. Create
![Uploading image.png…]()

* Task 2 - Enable SSPR for you test group

1. Entra admin center > Identity > Protection > Password reset > Self sevice password reset enabled (Selected로 설정) 
2. Select group에 Task 1에서 만든 그룹 할당
3. 설정 완료  
