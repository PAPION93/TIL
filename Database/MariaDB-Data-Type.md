# MariaDB Data Type
> 2020-03-16 최초 정리  
> 추가 필요

## [TEXT] Type Document
### 문법
`TEXT[(M)] [CHARACTER SET charset_name] [COLLATE collation_name]`  

### 설명
가변 데이터, 최대길이 65,636( 2^16 - 1 )  
M 옵션으로 길이 조정 가능하다.  
collation은 PADSPACE 유형이다. 즉 데이터 비교시 후행공백은 모두 무시한다. LIKE 연산자에서는 다르다.  
MariaDB 10.2.1 전에는 DEFAULT 를 지정할 수 없었지만 10.2.1부터는 가능하다.  

후행공백 예제:
```
CREATE TABLE strtest (d TEXT(10));
INSERT INTO strtest VALUES('Maria   ');

SELECT d='Maria',d='Maria   ' FROM strtest;
+-----------+--------------+
| d='Maria' | d='Maria   ' |
+-----------+--------------+
|         1 |            1 |
+-----------+--------------+

SELECT d LIKE 'Maria',d LIKE 'Maria   ' FROM strtest;
+----------------+-------------------+
| d LIKE 'Maria' | d LIKE 'Maria   ' |
+----------------+-------------------+
|              0 |                 1 |
+----------------+-------------------+
```

### VARCHAR 와 TEXT의 차이
- VARCHAR 칼럼은 완전히 인덱싱할 수 있지만, TEXT 칼럼은 지정된 길이만 인덱스를 탈 수 있다.  