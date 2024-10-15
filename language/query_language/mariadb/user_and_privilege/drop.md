# 사용자 삭제

- `DROP USER` 키워드를 사용하여서 존재하는 사용자를 삭제할 수 있다.

  ```sql
  DROP USER `사용자명`@`호스트명`;
  ```

  > 사용자명이 `test`이고, 호스트명이 `localhost`인 사용자를 삭제하는 쿼리는 아래와 같다.
  >
  > ```sql
  > DROP USER `test`@`localhost`;
  > ```
