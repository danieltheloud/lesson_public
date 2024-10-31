# 제약조건 추가

## 기본키 추가

- `ADD PRIMARY KEY` 키워드를 사용해서 `기본키`를 추가할 수 있다.
- `기본키`를 추가하는 조건은 테이블을 생성할 때와 동일하다.
  - 기본키로 지정될 열은 `NOT NULL`이어야 함에 유의한다.

  ```sql
  ADD PRIMARY KEY (`열 이름`, ...)
  ```

## 외래키 추가

- `ADD FOREIGN KEY` 키워드를 사용해서 `외래키`를 추가할 수 있다.
- `외래키`를 추가하는 조건은 테이블을 생성할 때와 동일하다.

  ```sql
  ADD [CONSTRAINT [제약조건 이름]] FOREIGN KEY (`참조 열`, ...)
          REFERENCES `피참조 스키마`.`피참조 테이블` (`피참조 열`, ...)
      [ON DELETE CASCADE]
      [ON UPDATE CASCADE]
  ```

## 고유키 추가

- `ADD UNIQUE` 키워드를 사용해서 `고유키`를 추가할 수 있다.
- `고유키`를 추가하는 조건은 테이블을 생성할 때와 동일하다.

  ```sql
  ADD [CONSTRAINT [제약조건 이름]] UNIQUE (`열 이름`, ...)
  ```

## 체크 제약조건 추가

- `ADD CHECK` 키워드를 사용해서 `체크` 제약조건을 추가할 수 있다.

  ```sql
  ADD [CONSTRAINT [제약조건 이름]] CHECK (조건)
  ```
