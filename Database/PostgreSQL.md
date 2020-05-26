# PostgreSQL

## Data Type

- Numeric Type

  | Name        | Storage Size | Description                        |
  | ----------- | ------------ | ---------------------------------- |
  | smallint    | 2bytes       | small-range integer                |
  | integer     | 4bytes       | typical choice for integer         |
  | bigint      | 8bytes       | large-range integer                |
  | smallserial | 2bytes       | small **autoincrementing** integer |
  | serial      | 4bytes       | **autoincrementing** integer       |
  | bigserial   | 8bytes       | large **autoincrementing** integer |

- Character Type

  1. varchar(n) : 가변 길이
  1. char(n) : 고정 길이, 공백 추가
  1. text : 무제한 가변 길이

- Date/Time Type  

  ![datetime](https://github.com/PAPION93/TIL/blob/master/img/psql-datetype.png)

- Boolean Type

  | Name    | Storage Size | Description            |
  | ------- | ------------ | ---------------------- |
  | boolean | 1byte        | state of true or false |

- Enumerated Type  
  `CREATE TYPE week AS ENUM ('Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun');`

---

## User

### Create User

- `CREATE USER name [ [ WITH ] option [ ... ] ]`
- [옵션 참고](https://www.postgresql.org/docs/9.6/sql-createuser.html)
  > SUPERUSER | NOSUPERUSER  
  > CREATEDB | NOCREATEDB  
  > CREATEROLE | NOCREATEROLE

### Select User

- `SELECT * FROM PG_USER` , `\du`

---

## Database

### Create
```
create database database_name OWNER test_user;

CREATE DATABASE name [ [ WITH ] [ OWNER [=] user_name ]
[ TEMPLATE [=] template ]
[ ENCODING [=] encoding ]
[ LC_COLLATE [=] lc_collate ]
[ LC_CTYPE [=] lc_ctype ]
[ TABLESPACE [=] tablespace_name ]
[ ALLOW_CONNECTIONS [=] allowconn ]
[ CONNECTION LIMIT [=] connlimit ]
[ IS_TEMPLATE [=] istemplate ] ]
```

### Show Databases
  - `\l`

### Use Database
  - `\c testdb;`

### Show Tables
  - `\d`

### DESC Table
  - `\d table_name`
