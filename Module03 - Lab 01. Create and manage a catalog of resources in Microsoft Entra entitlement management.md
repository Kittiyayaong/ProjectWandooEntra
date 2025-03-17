# Module 03 - Plan and Implement and Identity Governance Strategy
## 01. Create and manage a catalog of resources in Microsoft Entra entitlement management

### 시나리오 
카탈로그는 리소스와 액세스 패키지의 컨테이너입니다. 관련 리소스를 그룹화하고 패키지에 액세스하려면 카탈로그를 생성합니다. 카탈로그를 생성하는 사람은 누구나 첫 번째 카탈로그 소유자가 됩니다. 카탈로그 소유자는 카탈로그 소유자를 추가할 수 있습니다. 조직에서 카탈로그를 생성하고 구성해야 합니다.

#### Exercise 1 - Building out resources in Entitlement Management
* Task 1 - Create a catalog

---

Tips. Catalog 

Catalog는 Microsoft Entra Identity Governance의 중요한 구성 요소로, 조직 내에서 리소스와 애플리케이션을 관리하고 제공하는 데 사용됩니다. Catalog는 다양한 리소스와 애플리케이션을 포함하며, 이를 통해 조직은 사용자에게 필요한 리소스를 쉽게 제공할 수 있습니다1.

Catalog의 주요 기능

* 리소스 관리: 조직 내에서 사용되는 애플리케이션, 팀, SharePoint 사이트, 그룹 등을 포함한 다양한 리소스를 관리할 수 있습니다.
* 접근 패키지: Access Packages를 통해 사용자에게 필요한 리소스를 패키지로 제공할 수 있습니다. 이를 통해 사용자는 필요한 리소스에 쉽게 접근할 수 있습니다
* 동적 그룹: Dynamic Groups를 사용하여 사용자의 속성에 따라 자동으로 그룹 멤버십을 관리할 수 있습니다. 이를 통해 조직은 효율적으로 그룹을 관리할 수 있습니다

---

![image](https://github.com/user-attachments/assets/4ffd0d99-1417-41dc-84c1-18c2bfb4123e)

1. Entra admin > Identity Governance > Entitlement management > Catalogs > New catalog
2. 설정값
   * Name: Wandoo Catalog
   * DescriptionL Wandoo Catalog
   * Eanbled: yes
   * Enabled for external users: no (이 설정을 사용하면 선택한 외부 디렉토리의 사용자가 이 카탈로그에서 액세스 패키지를 요청할 수 있습니다. 이 설정은 변경되지 않습니다.)


* Task 2 - Add resources to a catalog
  
액세스 패키지에 리소스를 포함하려면 리소스가 카탈로그에 존재해야 합니다. 추가할 수 있는 리소스 유형은 그룹, 애플리케이션 및 쉐어포인트 온라인 사이트입니다. 그룹은 클라우드로 생성된 Microsoft 365 그룹 또는 클라우드로 생성된 Microsoft Entra 보안 그룹일 수 있습니다. 애플리케이션은 SaaS 애플리케이션과 Microsoft Entra ID에 연합된 자체 애플리케이션을 포함한 Microsoft Entra 엔터프라이즈 애플리케이션일 수 있습니다. 사이트는 쉐어포인트 온라인 사이트 또는 쉐어포인트 온라인 사이트 일 수 있습니다.

1. task 1에서 생성한 catalog 클릭 > Resource 클릭 > 그룹과 팀, 애플리케이션, SharePoint 사이트와 같은 리소스 종류를 선택
![image](https://github.com/user-attachments/assets/2fc609f1-a9b5-465a-b489-58cb1f9bf560)
2. 설정값 예시 
![image](https://github.com/user-attachments/assets/1fea65e6-1a54-4101-9cc0-5e879c82fd5e)


* Task 3 - Add additional catalog owners
  
카탈로그를 생성한 사용자가 첫 번째 카탈로그 소유자가 됩니다. 카탈로그 관리를 위임하려면 사용자를 카탈로그 소유자 역할에 추가해야 합니다. 이렇게 하면 카탈로그 관리 책임을 공유할 수 있습니다.

1. catalog > Roles and administrators > Add catalog owner
2. Wandoo-user1을 선택 후 설정 완료
