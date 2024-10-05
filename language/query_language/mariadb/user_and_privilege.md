# 사용자 및 권한

## 사용자(user)

- 사용자는 DBMS 서버에 접속하여 각종 쿼리를 실행할 수 있는 주체를 의미한다.
- DBMS 설치 시, 최고 관리자 권한을 가지는 사용자인 `root`가 존재하게 된다.

### 사용자 생성

- `CREATE USER` 키워드를 사용하여서 새로운 사용자를 생성할 수 있다.

   ```sql
   CREATE USER `사용자명`@`호스트명` IDENTIFIED BY '비밀번호';
   ```

   > 사용자명이 `test`이고, 호스트명이 `localhost`이며, 비밀번호가 `test1234`인 사용자를 만드는 쿼리는 아래와 같다.
   >
   > ```sql
   > CREATE USER `test`@`localhost` IDENTIFIED BY 'test1234';
   > ```

### 사용자 조회

- `SELECT` 키워드를 사용하여서 현재 DBMS 상에 존재하는 사용자를 조회할 수 있다.
  - `SELECT`는 `레코드`를 조회하기 위한 키워드로써, `레코드`에 대한 설명에서 다시 다룬다.

  ```sql
  SELECT `user`, `host` FROM `mysql`.`user`;
  ```

### 사용자 수정

- `ALTER USER` 키워드를 사용하여서 존재하는 사용자의 비밀번호를 수정할 수 있다.

  ```sql
  ALTER USER `사용자명`@`호스트명` IDENTIFIED BY '새로운 비밀번호';
  ```

  > 사용자명이 `test`이고, 호스트명이 `localhost`인 사용자의 비밀번호를 `password`로 수정하는 쿼리는 아래와 같다.
  >
  > ```sql
  > ALTER USER `test`@`localhost` IDENTIFIED BY 'password';
  > ```

### 사용자 삭제

- `DROP USER` 키워드를 사용하여서 존재하는 사용자를 삭제할 수 있다.

  ```sql
  DROP USER `사용자명`@`호스트명`;
  ```

  > 사용자명이 `test`이고, 호스트명이 `localhost`인 사용자를 삭제하는 쿼리는 아래와 같다.
  >
  > ```sql
  > DROP USER `test`@`localhost`;
  > ```

## 권한

### 권한 부여

- `GRANT` 키워드를 사용하여서 존재하는 사용자에게 권한을 부여할 수 있다.

  ```sql
  GRANT 권한, ... ON 스키마 이름.테이블 이름 TO `사용자명`@`호스트명`;
  ```

  - 권한에는 `CREATE`, `ALTER`, `DROP`, `SELECT`, `INSERT`, `UPDATE`, `DELETE` 등이 있다.
  - 권한은 쉼표(`,`)로 구분하여 동시에 작성할 수 있다.
  - 권한으로 `ALL`을 (또는 `ALL PRIVILEGES`를) 주게 되면, `GRANT`를 제외한 모든 권한을 부여한다.
    - `GRANT` 권한을 부여하려면 마지막에 `WITH GRANT OPTION`을 추가해야 하며, 해당 사용자는 (자신을 포함한) 모든 사용자에게 권한을 부여할 수 있는 권한을 부여받게 된다.
  - 스키마 이름 및 테이블 이름에 애스터리스크(`*`)를 사용할 경우, 모든 스키마 혹은 모든 테이블을 의미하게 된다.

    > 모든 스키마와 테이블에 대하여, `test`@`localhost` 계정에게 (`GRANT`를 포함한) 모든 권한을 부여하려면 아래 쿼리를 실행한다.
    >
    > ```sql
    > GRANT ALL ON *.* TO `test`@`localhost` WITH GRANT OPTION;
    > ```

### 권한 조회

- `SHOW` 키워드를 사용하여서 현재 접속 중인 사용자의 권한을 확인할 수 있다.
  
  ```sql
  SHOW GRANTS;
  ```

- `FOR` 키워드를 사용하여서 다른 사용자의 권한을 확인할 수 있다.

  ```sql
  SHOW GRANTS FOR `사용자명`@`호스트명`;
  ```

### 권한 철회

- `ROVOKE` 키워드를 사용하여서 어떤 사용자가 가지고 있는 권한을 철회할 수 있다.

  ```sql
  REVOKE 권한, ... ON 스키마 이름.테이블 이름 FROM `사용자명`@`호스트명`;
  ```

  - `GRANT` 권한을 철회하려면 `GRANT OPTION`을 입력한다.
