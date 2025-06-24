# Module 03 - Plan and Implement and Identity Governance Strategy
## 01. Create and manage a catalog of resources in Microsoft Entra entitlement management

### Lab 설명 

1. Catalog란? 리소스 카탈로그는 관련된 리소스와 액세스 패키지를 그룹화하는 컨테이너입니다. 관리자는 카탈로그를 생성할 수 있으며, 카탈로그 생성자 역할로 위임된 사용자도 자신이 소유한 리소스에 대해 카탈로그를 생성할 수 있습니다

2. 카탈로그의 주요 기능 및 목적
* 리소스 그룹화: 관련된 리소스와 액세스 패키지를 그룹화하여 관리합니다
* 액세스 패키지 관리: 사용자가 요청할 수 있는 액세스 패키지를 생성하고 관리합니다.
* 외부 사용자 지원: 외부 디렉토리의 사용자가 액세스 패키지를 요청할 수 있도록 지원합니다

3. 추가 정보
* [Create and manage a catalog of resources in entitlement management](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-catalog-create)

## ✅ Exercise 1 - Building out resources in Entitlement Management
* Task 1 - Create a catalog

---

> ⭐️ Tips. Catalog
> 어떤 리소스들에 대한 접근 권한을 줄 건지 묶어두는 상자. 카탈로그는 Access Package의 리소스를 담는 상자이며, 조직 내 접근 거버넌스의 시작점이 됩니다. Access Package를 만들려면 먼저 이 카탈로그가 필요해요.

> ⭐️ 예시. HR-Catalog
>  * 리소스: HR Team SharePoint, HR Teams 그룹
>  * 외부 사용자 포함 안 함

> ⭐️ 예시. Partner-Catalog
>  * 리소스: Partner Collaboration Teams, PowerApps
>  * 외부 사용자 포함 ✔️

---

1. Entra admin > Identity Governance > Entitlement management > Catalogs > New catalog
2. 설정값
   * Name: Wandoo Catalog
   * DescriptionL Wandoo Catalog
   * Eanbled: yes
   * Enabled for external users: no (이 설정을 사용하면 선택한 외부 디렉토리의 사용자가 이 카탈로그에서 액세스 패키지를 요청할 수 있습니다)

  <img width="1184" alt="스크린샷 2025-06-24 오후 1 20 36" src="https://github.com/user-attachments/assets/5cc52722-90c1-46bc-866f-58b6028b3181" />

---

* Task 2 - Add resources to a catalog
  
액세스 패키지(Access Package)를 만들기 전에, 먼저 그 리소스를 카탈로그에 등록해야 합니다. 즉, 리소스를 액세스 패키지에 포함하려면 먼저 카탈로그에 추가되어야 해요.

> ⭐️ Tips. 어떤 리소스를 추가할 수 있나요?
>  * Groups and Teams: M365 그룹이나 Entra 보안 그룹 (예: Wandoo Sales)
>  * Applications: 엔터프라이즈 앱 (예: Box, Salesforce)
>  * SharePoint sites: 온라인 쉐어포인트 사이트 (예: Brand 관련 문서 사이트)

1. task 1에서 생성한 catalog 클릭 > Resource 클릭 > 그룹과 팀, 애플리케이션, SharePoint 사이트와 같은 리소스 종류를 선택

| Resource Type       | Value                                                        |
|---------------------|--------------------------------------------------------------|
| Groups and Teams    | Wandoo Sales                                                      |
| Applications        | Box                                                          |
| Applications        | Salesforce                                                   |
| SharePoint sites    | Brand - pick this SharePoint from your list of available sites |


---

* Task 3 - Add additional catalog owners
  
카탈로그를 생성한 사용자가 첫 번째 카탈로그 소유자가 됩니다. 카탈로그 관리를 위임하려면 사용자를 카탈로그 소유자 역할에 추가해야 합니다. 이렇게 하면 카탈로그 관리 책임을 공유할 수 있습니다.

1. catalog > Roles and administrators > Add catalog owner
2. **Wandoo-user1**을 선택 후 설정 완료

  <img width="1182" alt="image" src="https://github.com/user-attachments/assets/4da5b7f0-6147-40fe-b29b-f649ed19e57b" />
