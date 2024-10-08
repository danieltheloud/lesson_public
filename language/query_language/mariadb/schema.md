# 스키마(schema)

- 스키마는 서로 관련있는 테이블을 묶어내기 위해 사용한다.
- `SCHEMA`라는 단어는 데이터베이스(Database, `DATABASE`)라는 단어와 치환하여 사용할 수 있다.
- 실제 데이터를 포함하지 않는 단순한 껍데기일 뿐이다.
- 명명법 : `스네이크 케이스`, `단수형`

## 스키마 생성하기

- 스키마를 생성하기 위해 아래 쿼리를 실행한다.

  ```sql
  CREATE SCHEMA `스키마 이름`;
  ```

- 이미 존재하는 스키마의 이름으로 생성하려고 하면 오류가 발생하므로 유의한다.
  - 해당 스키마 이름이 존재하지 않는 경우에만 생성하려면, 아래와 같이 `IF NOT EXISTS` 키워드를 활용할 수 있다.

    ```sql
    CREATE SCHEMA IF NOT EXISTS `스키마 이름`;
    ```

## 조회하기

- 존재하는 모든 스키마를 조회하기 위해 아래 쿼리를 실행한다.

  ```sql
  SHOW SCHEMAS;
  ```

## 수정하기

- 스키마의 이름을 변경하는 것은 불가능하므로 유의한다.

## 삭제하기

- 스키마를 삭제하기 위해 아래 쿼리를 실행한다.

  ```sql
  DROP SCHEMA `스키마 이름`;
  ```

  > 스키마를 삭제하면, **포함되어 있던 테이블 및 레코드가 모두 삭제되어 되돌릴 수 없음**에 유의한다.
- 존재하지 않는 스키마를 삭제하려고 하면 오류가 발생하므로 유의한다.
  - 해당 스키마 이름이 존재하는 경우에만 삭제하려면, 아래와 같이 `IF EXISTS` 키워드를 활용할 수 있다.

  ```sql
  DROP SCHEMA IF EXISTS `스키마 이름`;
  ```
