# 권한 부여

- `GRANT` 키워드를 사용하여서 존재하는 사용자에게 권한을 부여할 수 있다.

  ```sql
  GRANT 권한, ... ON `스키마 이름`.`테이블 이름` TO `사용자명`@`호스트명`;
  ```

  - 권한에는 `CREATE`, `ALTER`, `DROP`, `SELECT`, `INSERT`, `UPDATE`, `DELETE` 등이 있다.
  - 권한은 쉼표(`,`)로 구분하여 동시에 작성할 수 있다.
  - 권한으로 `ALL` 또는 `ALL PRIVILEGES`를 주게 되면, `GRANT`를 제외한 모든 권한을 부여한다.
    - `GRANT` 권한을 부여하려면 마지막에 `WITH GRANT OPTION`을 추가해야 하며, 해당 사용자는 (자신을 포함한) 모든 사용자에게 권한을 부여할 수 있는 권한을 부여받게 된다.
  - 스키마 이름 및 테이블 이름에 애스터리스크(`*`)를 사용할 경우, 모든 스키마 혹은 모든 테이블을 의미하게 된다.

    > 모든 스키마와 테이블에 대하여, `test`@`localhost` 계정에게 (`GRANT`를 포함한) 모든 권한을 부여하려면 아래 쿼리를 실행한다.
    >
    > ```sql
    > GRANT ALL ON *.* TO `test`@`localhost` WITH GRANT OPTION;
    > ```
