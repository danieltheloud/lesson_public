# 테이블 수정

- `ALTER TABLE` 키워드를 사용해서, `테이블` 수정할 수 있다.

## 이름 변경

- `RENAME` 키워드를 사용해서, `테이블` 이름을 변경할 수 있다.

    ```sql
    ALTER TABLE `스키마 이름`.`기존 테이블 이름`
            RENAME `스키마 이름`.`새로운 테이블 이름`;
    ```

### 소속 스키마 변경

- `MySQL` 및 `MariaDB` DBMS에서 `스키마`의 이름을 변경하는 것은 **불가능**하다.

  ```sql
  ALTER TABLE `기존 스키마 이름`.`기존 테이블 이름`
          RENAME `새로운 스키마 이름`.`새로운 테이블 이름`;
  ```

  - `테이블`의 소속 `스키마`를 전체 변경하고, 기존의 `스키마`를 삭제하는 방식으로 `스키마`를 이동해야한다.

## 열 수정

- [열 추가](./column/add.md)
- [열 이름 변경](./column/rename.md)
- [열 구조 변경](./column/modify.md)
- [열 제거](./column/drop.md)

## 제약조건 수정

- [제약조건 추가](./constraint/add.md)
- [제약조건 제거](./constraint/drop.md)
