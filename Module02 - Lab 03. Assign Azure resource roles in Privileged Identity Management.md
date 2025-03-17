# Module 02 - Implement an Authentication and Access Management Solution
## 03. Assign Azure resource roles in Privileged Identity Management

### 시나리오 
Microsoft Entra Privileged Identity Management(PIM)는 내장된 Azure 리소스 역할뿐만 아니라 사용자 지정 역할도 관리할 수 있습니다

#### Exercise 1 - PIM with Azure resources
* Task 1 - Assign Azure resource roles

1. Entra admin > Identity governance > Privileged Identity Management > Azure resource
2. 해당되는 management group / Subscription / Resource group / Resource 선택 후 Manage resource 클릭
3. Manage > Roles로 > Add assignment 클릭

![image](https://github.com/user-attachments/assets/e62737d8-d65d-4681-8920-c18d2da2824e)

4. 'API Management Service Contributor' or 'Role based access control Administrator' 선택
5. Member 추가 후 next
6. Assignment type은 Eligible모드로 진행

---

Tips.

1. 적격 할당(Eligible assignments)은 역할의 구성원이 역할을 사용하기 위한 작업을 수행해야 합니다. 작업에는 다중 인증(MFA) 확인 수행, 비즈니스 정당성 제공 또는 지정된 승인자의 승인 요청이 포함될 수 있습니다.
2. 활성 할당(Active assignments)은 구성원이 역할을 사용하기 위해 어떤 작업도 수행할 필요가 없습니다. 활성으로 할당된 구성원은 항상 역할에 할당된 권한을 갖습니다.

---

