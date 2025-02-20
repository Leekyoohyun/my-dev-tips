## Error: 1205-HY000: Lock wait timeout exceeded;

홈페이지 메인으로 갈 때 
``` SQL
<!-- 접속로그 정보 등록 -->
	<insert id="insertAccessLogInfo" parameterType="dmap">
        INSERT INTO LMS_SY_ACCES_LOG (
			  ACCES_SEQ
			, SYS_GB
			, ACCES_URL 
			, ACCES_USERID 
			, ACCES_IP 
			, ACCES_DATE 
			, ACCES_YEAR
		) VALUES(
			  (SELECT NVL(MAX(A.ACCES_SEQ),0) + 1 FROM LMS_SY_ACCES_LOG A)
			, #{sysGb}
			, #{accesUrl}
			, #{accesUserId}
			, #{accesIp}
			, SYSDATE()
			, TO_CHAR(SYSDATE(), 'YYYY')
		)
    </insert>
```
해당 쿼리가 작동하면서 log를 남겨야하는데, 시간이 오래걸리면서 로그가 남지 않는 문제 발생.

-- 프로세스 목록 조회
``` SQL
SHOW PROCESSLIST;
```

-- PROCESS 권한 필요
``` SQL
SELECT * FROM information_schema.INNODB_LOCK_WAITS;
SELECT * FROM information_schema.INNODB_TRX;\
```
위 쿼리를 통해 확인해보니 새벽 5시부터 돌고있는 쿼리가 있다는 걸 알게됨.


``` SQL
kill [id]
```
를 통해서 해결 완료!
