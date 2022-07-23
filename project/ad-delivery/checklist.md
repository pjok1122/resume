### VM creation and application

| checklist        | description                                                   |
| ---------------- | ------------------------------------------------------------- |
| mongodb          | <ul><li>[x] 장비 생성</li><li>[x] Mongodb 설치 요청</li></ul> |
| mysql batch DB   | <ul><li>[x] 장비 생성</li><li>[x] 계정 생성</li></ul>         |
| Redis Cluster    | <ul><li>[x] 장비 생성</li>                                    |
| API/Batch Server | <ul><li>[x] RC장비 생성</li><li>[x] REAL 장비 생성</li></ul>  |
| Consumer Server  | <ul><li>[x] RC k8s 요청</li><li>[x] REAL k8s 요청</li></ul>   |

### ACL

| checklist   | description                                             |
| ----------- | ------------------------------------------------------- |
| DB ACL      | <ul><li>[x] MongoDB ACL</li><li>[x] Mysql ACL</li></ul> |
| network ACL | <ul><li>[x] 필요한지 전체 점검</li></ul>                |


### Security

| checklist                            | description                                                                                         |
| ------------------------------------ | --------------------------------------------------------------------------------------------------- |
| Credential Encryption                | <ul><li>[x] credential 암호화</li><li>[x] credential 복호화 검증</li></ul>                          |
| API Authentication                   | <ul><li>[x] 허용된 클라이언트에서만 접근할 수 있도록 인증 절차 추가 필요.</li></ul>                 |
| nginx white ip                       | <ul><li>[x] nginx에 white IP 처리</li></ul>                                                         |
| log credential encryption            | <ul><li>[ ] NELO같은 로그 시스템에 Client secret 같은 credential info가 남지 않도록 처리.</li></ul> |
| Save encrypted credential info to DB | <ul><li>[x] credential info를 DB에 저장할 때는 암호화된 값을 저장.</li></ul>                        |


### Infra

| checklist            | description                                                       |
| -------------------- | ----------------------------------------------------------------- |
| nginx 설정           | <ul><li>[x] nginx.conf 기본 설정</li></ul>                        |
| DNS                  | <ul><li>[x] 도메인 생성</li></ul>                                 |
| Load balancer        | <ul><li>[x] LB 생성 및 연동</li></ul>                             |
| NELO 연동            | <ul><li>[ ] 로그 시스템 연동</li></ul>                            |
| SSL 설정 확인        | <ul><li>[x] SSL 설정이 잘 되어있는지 확인. </li></ul>             |
| Monitoring Tool 연동 | <ul><li>[x] Prometheus 설정 </li><li>[ ] DevOps에 요청 </li></ul> |

### Deployment

| checklist          | description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| nginx/jdk 설치     | <ul><li>[x] JDK 설치</li><li>[x] nginx 설치</li></ul>                       |
| log rotate         | <ul><li>[x] spring boot log rotate</li><li>[x] nginx log rotate</li></ul>   |
| 배포 시나리오 생성 | <ul><li>[x] health down/up 설정</li><li>[x] consumer down/up 설정</li></ul> |


### Failover

| checklist        | description                                                      |
| ---------------- | ---------------------------------------------------------------- |
| mysql failover   | <ul><li>[x] DNS cache TTL 설정</li></ul>                         |
| redis failover   | <ul><li>[x] Redis Topology 적용 (Beta 환경에서 테스트)</li></ul> |
| mongodb failover | <ul><li>[x] Cluster 설정</li></ul>                               |

### Network isolation

| checklist              | description                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| outbound-gw 설정       | <ul><li>[x] Pay zone 밖으로 요청을 보낼 땐, outbound-gw를 통함.</li></ul>                   |
| internal-corps-gw 설정 | <ul><li>[x] Pay zone 밖에서 Pay zone으로 요청을 보낼 때 internal-corps-gw를 통함.</li></ul> |

### Qaulity

| checklist                | description                             |
| ------------------------ | --------------------------------------- |
| Sonarqube & Jenkins 연동 | <ul><li>[x] </li></ul>                  |
| Code Coverage            | <ul><li>[x] Coverage 90% 이상</li></ul> |
| 정적 결함                | <ul><li>[x] 정적결함 Zero</li></ul>     |

### Service

| checklist              | description                                              |
| ---------------------- | -------------------------------------------------------- |
| 배포 전 DML 처리       | <ul><li>[x] </li></ul>                                   |
| 인덱스 생성            | <ul><li>[ ] 인덱스 생성 요청</li></ul>                   |
| 점포 정보 마이그레이션 | <ul><li>[x] RC 환경에서 점포 정보 마이그레이션</li></ul> |
| Batch job schedule     | <ul><li>[x] RC 환경에서 배치 잡 설정</li></ul>           |
| Dummy Data Clear       | <ul><li>[ ] 테스트 데이터 삭제</li></ul>                 |
| Error Alert            | <ul><li>[ ] warn, error 로그에 대한 알람 설정</li></ul>  |
| PagerDuty              | <ul><li>[ ] DevOps에 PagerDuty 연동 요청</li></ul>       |
| Real QA support        | <ul><li>[x] 출시 전 Real QA를 위한 설정</li></ul>        |

### After deployment

| checklist                       | description                                                  |
| ------------------------------- | ------------------------------------------------------------ |
| internal-corps-gw endpoint 변경 | <ul><li>[ ] RC endpoint에서 Real endpoint로 변경 </li></ul>  |
| batch job schedule              | <ul><li>[ ] RC batch job off하고 Real batch job on</li></ul> |
| 점포 정보 마이그레이션          | <ul><li>[ ] Real 환경에서 점포 정보 마이그레이션</li></ul>   |