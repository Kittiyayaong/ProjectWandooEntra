# Module 03 - Plan and Implement and Identity Governance Strategy
## 01. Create and manage a catalog of resources in Microsoft Entra entitlement management

### Lab 설명 

1. 카탈로그(Catalog): 리소스(그룹, 앱, SharePoint 사이트 등)를 하나의 묶음으로 구성한 리소스 풀입니다. 일반적으로 조직 단위(예: 마케팅팀, HR팀 등) 또는 특정 용도 기반으로 카탈로그를 나눕니다.
2. 액세스 패키지(Access Package): 카탈로그 안의 리소스들 중 일부 또는 전체를 묶어서 제공하는 실제 액세스 요청 단위입니다. 액세스 패키지별로 요청 조건, 승인 프로세스, 만료, 자동 리뷰 등의 정책을 지정합니다.

> ⭐️ 예시: 마케팅팀 구성
> 
| 계층                      | 설명                                                                     |
| ----------------------- | ---------------------------------------------------------------------- |
| 📂 **Catalog: 마케팅**     | `Teams 채널`, `SharePoint`, `Salesforce`, `디자인 툴`, `캠페인용 Azure 리소스` 등 포함 |
| 📦 **Access Package 1** | *마케팅 인턴용 패키지* (SharePoint + Teams만 제공)                                 |
| 📦 **Access Package 2** | *마케팅 매니저용 패키지* (모든 리소스 제공, 승인 필요)                                      |
| 📦 **Access Package 3** | *광고 캠페인용 임시 액세스 패키지* (Salesforce, 디자인 툴, 기간 제한 + Access Review 포함)     |

> ⭐️ 핵심 
>  * Access Package는 항상 하나의 Catalog 내에서만 생성됩니다.
>  * 하나의 Catalog에 여러 Access Package를 만들 수 있습니다.
>  * 따라서, “마케팅”이라는 Catalog에서 직급/용도에 맞는 여러 Access Package를 분기해 만들 수 있습니다.

3. 추가 정보
* [Create and manage a catalog of resources in entitlement management](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-catalog-create)

---

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
  
카탈로그는 기본적으로 생성한 사용자가 소유자가 됩니다. 그런데 여러 명이 함께 관리해야 할 때, 다른 사용자에게도 '카탈로그 소유자' 역할을 추가할 수 있습니다. (운영자가 한 명이면 위험 → 운영을 분산해서 리스크 최소화)

1. catalog > Roles and administrators > Add catalog owner
2. **Wandoo-user1**을 선택 후 설정 완료

  <img width="1182" alt="image" src="https://github.com/user-attachments/assets/4da5b7f0-6147-40fe-b29b-f649ed19e57b" />
