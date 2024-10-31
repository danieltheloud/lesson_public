# 사용자 수정

- `ALTER USER` 키워드를 사용해서 존재하는 사용자의 비밀번호를 수정할 수 있다.

  ```sql
  ALTER USER `사용자명`@`호스트명` IDENTIFIED BY '새로운 비밀번호';
  ```

  > 사용자명이 `test`이고, 호스트명이 `localhost`인 사용자의 비밀번호를 `password`로 수정하는 쿼리는 아래와 같다.
  >
  > ```sql
  > ALTER USER `test`@`localhost` IDENTIFIED BY 'password';
  > ```
