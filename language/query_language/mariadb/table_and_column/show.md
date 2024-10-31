# 테이블 조회

- `SHOW TABLES` 키워드를 사용해서, 특정 `스키마`에 소속된 `테이블`을 조회할 수 있다.

  ```sql
  SHOW TABLES IN `스키마 이름`;
  ```

## 열 조회

- `SHOW COLUMNS` 키워드를 사용해서, `테이블`의 열 구조를 조회할 수 있다.

  ```sql
  SHOW COLUMNS IN `테이블 이름`;
  ```

- `DESC` 키워드를 사용하여도, `테이블`의 열 구조를 조회할 수 있다.

  ```sql
  DESC `스키마 이름`.`테이블 이름`;
  ```

  > `DESC`는 describe를 뜻한다.
