# 사용자 생성

- `CREATE USER` 키워드를 사용하여서 새로운 사용자를 생성할 수 있다.

   ```sql
   CREATE USER `사용자명`@`호스트명` IDENTIFIED BY '비밀번호';
   ```

   > 사용자명이 `test`이고, 호스트명이 `localhost`이며, 비밀번호가 `test1234`인 사용자를 만드는 쿼리는 아래와 같다.
   >
   > ```sql
   > CREATE USER `test`@`localhost` IDENTIFIED BY 'test1234';
   > ```
