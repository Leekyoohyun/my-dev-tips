## 지난번에 쿼리 하나가 돌고 있어서 kill 명령을 통해 죽였다고 했는데, 또 한번 이 문제가 발생하여 원인을 알아보았다.

### 1. 동시성 이슈 시나리오
서로 다른 두명이(IP 동일) 동시에 DB에 쿼리를 날리게 됨.

--> Lock이 걸림.

![Image](https://github.com/user-attachments/assets/a060d707-b765-417e-8228-c6754c7aaae0)

### 2. Transcation & Lock
- Transaction 이란, 데이터베이스의 상태를 변화시키기 위해 수행하는 작업의 단위를 뜻합니다. (select, insert, delete, update)
- Lock은 트랜잭션 처리의 순차성을 보장하기 위한 방법입니다. DBMS 마다 락을 구현하는 방식과 세부적인 방법이 다릅니다.

