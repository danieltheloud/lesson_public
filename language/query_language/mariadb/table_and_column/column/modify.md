# 열 구조 수정하기

- `MODIFY COLUMN` 키워드를 사용해서, `열`의 구조를 수정할 수 있다.

  ```sql
  ALTER TABLE `스키마 이름`.`테이블 이름`
          MODIFY COLUMN `대상 열 이름` 이름을 제외한 열 구조;
  ```

  - `열` 구조 수정과 동시에 `FIRST` 및 `AFTER` 키워드를 사용해서 위치를 옮길 수도 있다.
