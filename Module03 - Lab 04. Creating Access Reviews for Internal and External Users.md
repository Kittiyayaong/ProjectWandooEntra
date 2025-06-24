# Module 03 - Implement Access Management for Apps
## 04. Creating Access Reviews for Internal and External Users

### Lab 설명 

1. Access Review란? 
Access Reviews는 Microsoft Entra ID Governance의 핵심 기능 중 하나로, 조직 내 사용자들이 여전히 특정 리소스(예: 그룹, 애플리케이션 등)에 접근할 필요가 있는지를 주기적으로 검토하도록 합니다.



#### Exercise 1 - Create an internal Access review
* Task - Create a new Access review

1. Entra Admin > Identity Governance > Access revice > New access review

   <img width="1437" alt="스크린샷 2025-06-24 오후 1 45 40" src="https://github.com/user-attachments/assets/b801367f-1dcc-414e-9d75-681d7b84aa96" />

2. Review Type 설정

  <img width="1180" alt="스크린샷 2025-06-24 오후 1 48 00" src="https://github.com/user-attachments/assets/09b99ea8-36e4-4851-bbe4-902100b666b1" />

   * Select what to review: Terms + Groups
   * Review Scope: All Microsoft 365 groups with guest users
   * Scope: Guest users only
     
3. Reviews 설정

## Access Review 설정 요약

| 설정 항목                    | 설정값                          | 의미 설명 |
|-----------------------------|----------------------------------|-----------|
| **Multi-stage review**      | ❌ 비활성화                     | 리뷰 단계를 한 번만 수행하며, 다단계 검토는 설정하지 않음 |
| **Select reviewers**        | Group owner(s)                  | 해당 그룹의 소유자가 리뷰어로 지정됨 |
| **Fallback reviewers**      | (선택되지 않음)                 | 지정된 리뷰어가 리뷰를 완료하지 못할 경우 대신 검토할 사용자 지정 (지정하지 않음) |
| **Duration (in days)**      | 3                                | 리뷰 기간은 각 반복마다 3일 동안 진행됨 |
| **Review recurrence**       | Monthly                          | 검토 주기가 월 단위로 반복됨 |
| **Start date**              | 2025-06-24                       | Access Review가 시작되는 날짜 |
| **End**                     | End after number of occurrences  | 지정된 횟수만큼 반복 후 종료됨 |
| **Occurrences**             | 15                               | 총 15회 반복되며, 이후 자동 종료됨 |

  <img width="1178" alt="스크린샷 2025-06-24 오후 1 49 59" src="https://github.com/user-attachments/assets/316ab1e4-9268-437b-b2a2-43339e7c8e82" />

  5. 설정완료



### 🔗 [다음 Lab으로 이동하기 »](https://github.com/Kittiyayaong/ProjectWandooEntra/blob/main/Module03%20-%20Lab%2005.%20Configure%20Privileged%20Identity%20Management%20for%20Microsoft%20Entra%20roles.md)
