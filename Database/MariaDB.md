# MariaDB 꿀팁들을 정리해보자 
> Real MariaDB 를 읽고 알게된 내용을 작성한다.

### 91p. 온라인 스키마 변경
 - `ALTER ONLINE TABLE ...`
 > MariaDB 10.0 버전부터 사용가능  
 > ALTER TABLE 중에도 다른 커넥션의 INSERT, UPDATE, DELETE 문장들이 대기상태로 빠지지않고 즉시 처리된다.
 
### 93p. XtraDB 스토리지 엔진은 Mysql 5.6 의 InnoDB 스토리지 엔진을 개선한 버전이다.

### 242p. 쿼리의 실행 계획이 좋은 경우
 - Distinct
 - Using index
 - Using index for group-by
> 해당 항목들은 최적화되어 처리됨을 알 수 있음. 특히 두번째는 커버링 인덱스로 처리됨을 알려주는데, 최고의 성능을 보여준다.

### 245p. 리드 어헤드(Read ahead) 튜닝
 - innodb_read_ahead_threshold 값을 줄여 더 빈번하게 발생되도록 유도 가능