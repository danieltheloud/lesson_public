# 사용자 조회

- `SELECT` 키워드를 사용해서 현재 DBMS 상에 존재하는 사용자를 조회할 수 있다.
  - `SELECT`는 `레코드`를 조회하기 위한 키워드로써, `레코드`에 대한 설명에서 다시 다룬다.

  ```sql
  SELECT `user`, `host` FROM `mysql`.`user`;
  ```
