# Module 02 - Implement an Authentication and Access Management Solution
## 03. Assign Azure resource roles in Privileged Identity Management

### Lab 설명 
Microsoft Entra Privileged Identity Management (PIM)에서 Azure 리소스 역할 할당은 조직의 중요한 리소스에 대한 접근을 관리, 제어 및 모니터링하는 데 사용됩니다. 이 기능은 Azure 리소스에 대한 역할을 할당하고, 이러한 역할에 대한 조건을 설정하며, 역할을 활성화하는 과정을 포함합니다.

1. 주요 기능 및 목적
* 역할 할당: 사용자가 Azure 리소스에 대한 특정 역할을 할당받을 수 있습니다. 예를 들어, Owner, User Access Administrator, Contributor, Security Admin, Security Manager 등의 역할이 있습니다.
* 조건 설정: Azure 속성 기반 접근 제어(Azure ABAC)를 사용하여 역할 할당에 조건을 추가할 수 있습니다. 이를 통해 사용자의 역할 권한을 세밀하게 제한하고, 시간 제한 설정, 승인 워크플로우, 감사 기록 등을 통해 보안을 강화할 수 있습니다.
* 역할 활성화: 사용자가 특정 작업을 수행하기 위해 역할을 활성화해야 하는 경우, 다중 인증(MFA) 확인, 비즈니스 정당성 제공, 지정된 승인자로부터 승인 요청 등의 추가 조치를 요구할 수 있습니다.

2. 관련 자료
* [Assign Azure resource roles in Privileged Identity Management](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-resource-roles-assign-roles)
* [Activate my Azure resource roles in Privileged Identity Management](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-resource-roles-activate-your-roles)

#### Exercise 1 - PIM with Azure resources
* Task 1 - Assign Azure resource roles

1. Entra admin > Identity governance > Privileged Identity Management > Azure resource
![image](https://github.com/user-attachments/assets/8c47ecf1-dc7b-40b9-b206-629def7686da)

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

7. 특정 할당 기간을 지정하려면 시작 날짜와 종료 날짜 및 시간을 변경합니다. (max 1year)
![image](https://github.com/user-attachments/assets/9dd7d7ac-3aa1-4303-88db-9ce337c47dd2)

8. 설정 완료 

