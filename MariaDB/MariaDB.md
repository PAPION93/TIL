# MariaDB 꿀팁들을 정리해보자 
> Real MariaDB 를 읽고 알게된 내용을 작성한다.

### 242p. 쿼리의 실행 계획이 좋은 경우
 - Distinct
 - Using index
 - Using index for group-by
> 해당 항목들은 최적화되어 처리됨을 알 수 있음. 특히 두번째는 커버링 인덱스로 처리됨을 알려주는데, 최고의 성능을 보여준다.

### 245p. 리드 어헤드(Read ahead) 튜닝
 - innodb_read_ahead_threshold 값을 줄여 더 빈번하게 발생되도록 유도 가능