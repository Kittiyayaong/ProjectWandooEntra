# Module 02 - Implement an Authentication and Access Management Solution
## 05. Configure an Multifactor authentication registration policy

### Lab 설명
MFA(다중 인증) 등록을 사용자에게 사전 강제로 적용하여 보안을 강화하는 시나리오를 다룹니다

##### 목적
조직 사용자들이 보안 강화를 위해 **MFA 등록(MFA registration)** 을 반드시 하도록 요구하는 정책을 설정합니다. 사용자가 로그인 시점에만 MFA 등록을 강제하는 것이 아니라, **미리 등록하도록 유도/강제**함으로써 인증 흐름에서의 리스크를 최소화합니다.

##### Registration Campaign 이란?
Registration campaign은 아직 등록하지 않은 사용자에게 MFA(다단계 인증) 수단 등록을 유도하는 안내를 로그인 시점에 자동으로 표시함으로써, 조직 내 모든 사용자가 안전한 인증 수단을 등록하게 만들기 위한 기능입니다. 관리자가 캠페인을 활성화하면, 사용자가 로그인할 때마다 Microsoft Authenticator 등록을 유도하는 화면이 뜨고, 사용자는 최대 몇 번까지 '나중에 하기(snooze)'가 가능하지만, 설정된 횟수가 지나면 등록하지 않으면 로그인 불가 상태가 됩니다.

---

## ✅ Exercise 1 - Set up MFA registration policy
* Task 1 - Policy configuration

1. Entra admin > Identity > Protection > Authentication Methods > Registration campaign로 이동합니다.
2. 설정값 

| 설정 항목                     | 설정값               | 설명 |
|------------------------------|----------------------|------|
| **State**                    | Microsoft managed    | Microsoft에서 권장하는 기본 정책 상태. 캠페인이 활성화되어 사용자가 인증 수단을 등록하도록 유도됩니다. |
| **Days allowed to snooze**   | 1 day                | 사용자가 캠페인 알림을 연기할 수 있는 일수입니다. 1일로 설정 시 하루 후 다시 알림이 표시됩니다. |
| **Limited number of snoozes**| Enabled              | 사용자가 snooze할 수 있는 횟수를 제한합니다. ‘Enabled’로 설정 시, 반복 연기가 제한되며 결국 등록을 완료해야 합니다. |
| **Excluded users and groups**| None selected        | 캠페인 대상에서 제외할 사용자/그룹입니다. 기본적으로 모두 포함되며, 필요 시 예외를 추가할 수 있습니다. |
| **Authentication method**    | Microsoft Authenticator (All users) | 등록을 유도할 인증 수단입니다. 현재 Microsoft Authenticator를 모든 사용자에게 적용하도록 구성됩니다. |

- 모든 사용자는 로그인 시 Microsoft Authenticator 등록 요청을 받게 되며, 연기(snooze)가 제한됩니다.
- 더 안전한 인증 수단을 필수로 등록하도록 유도하여 조직 보안을 강화할 수 있습니다.

> ⚠️ 참고: 이 기능은 현재 Microsoft Authenticator에만 적용되며, FIDO2 키나 기타 인증 방법에는 적용되지 않습니다.

  <img width="1167" alt="스크린샷 2025-06-24 오후 1 08 58" src="https://github.com/user-attachments/assets/eee2a518-6bc1-49fb-b242-c5bb1796b5e8" />


> ⭐️ Tips. 등록 인터럽트
사용자가 Microsoft Entra가 연결된 애플리케이션(예: Teams, Outlook Web, SharePoint 등)에 로그인할 때, MFA(다단계 인증) 등록이 되어 있지 않으면 시스템이 자동으로 등록하라는 알림을 보여줍니다. 이 알림은 **로그인 프로세스 도중에 나타나는 인터럽트(중단)**입니다. 등록이 완료될 때까지 지속적으로 반복 노출됩니다 (다만, 설정된 snooze 기간만큼 미룰 수 있음).

  ![image](https://github.com/user-attachments/assets/56323738-3516-4ce4-bcc2-aef93e8f1373)


### 🔗 Module 02 완료 


