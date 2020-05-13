# MariaDB 꿀팁들을 정리해보자

> Real MariaDB 를 읽고 알게된 내용을 작성한다.

## 91p. MariaDB 온라인 스키마 변경

- `ALTER ONLINE TABLE ...`
  > MariaDB 10.0 버전부터 사용가능  
  > ALTER TABLE 중에도 다른 커넥션의 INSERT, UPDATE, DELETE 문장들이 대기상태로 빠지지않고 즉시 처리된다.

## 93p. XtraDB 스토리지 엔진은 Mysql 5.6 의 InnoDB 스토리지 엔진을 개선한 버전이다.

## 93p. Mysql 온라인 스키마 변경

- `LOCK = { DEFAULT | NONE | SHARED | EXCLUSIVE }`
  > DDL 실행중 다른커넥션의 읽기 쓰기를 허용하려면 NONE, 읽기만 허용은 SHARED
- `ALGORITHM = { DEFAULT | INPLACE | COPY }`
  > COPY는 임시테이블 복사->스키마변경->레코드복사->테이블 RENAME 방식  
  > INPLACE
  1. 스토리지 엔진 테이블인지 확인
  2. 스키마 변경 준비
  3. 스키마 변경 및 새로운 DML 로깅
     - DML 로그를 메모리에 저장한다. `innodb_online_alter_log_max_size` 으로 메모리크기 수정
  4. 로그 적용
  5. 스키마 변경완료 COMMIT
- persona 의 pt-online-schema-change 도구도 존재한다.
  > 초당 1500 SELECT, 270 INSERT, UPDATE, DELETE 테스트시 MariaDB 10.0, Mysql 5.6의 온라인스키마 변경보다 시간은 2배이상 걸렸지만, 보다 안정적인 쿼리와 CPU 상태를 볼 수 있다.

## 242p. 쿼리의 실행 계획이 좋은 경우

- Distinct
- Using index
- Using index for group-by
  > 해당 항목들은 최적화되어 처리됨을 알 수 있음. 특히 두번째는 커버링 인덱스로 처리됨을 알려주는데, 최고의 성능을 보여준다.

## 245p. 리드 어헤드(Read ahead) 튜닝

- innodb_read_ahead_threshold 값을 줄여 더 빈번하게 발생되도록 유도 가능
