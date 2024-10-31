# 제약조건 제거

## 기본키 제거

- `DROP PRIMARY KEY` 키워드를 사용해서 `기본키`를 제거할 수 있다.

  ```sql
  DROP PRIMARY KEY
  ```

## 외래키 제거

- `DROP FOREIGN KEY` 키워드를 사용해서 `외래키`를 제거할 수 있다.

  ```sql
  DROP FOREIGN KEY [제약조건 이름]
  ```

## 고유키 제거

- `DROP INDEX` 키워드를 사용해서 `고유키`를 제거할 수 있다.

  ```sql
  DROP INDEX [제약조건 이름]
  ```

## 체크 제약조건 제거

- `DROP CHECK` 키워드를 사용해서 `체크` 제약조건을 제거할 수 있다.

  ```sql
  DROP CHECK [제약조건 이름]
  ```
