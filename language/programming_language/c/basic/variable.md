# 변수와 상수

## 식별자(identifier)

> 식별자는 영어 대소문자, 숫자, 언더바(_)를 포함할 수 있다.

- 변수(variable)
  - 변수의 실체는 메모리의 특정 위치이다.
  - 변수는 값이 변할 수 있는 수이다.
  - 명명법: `카멜 케이스`
- (심볼릭) 상수
  - 상수는 값이 변할 수 없는 수이다.
  - 명명법: `어퍼 스네이크 케이스`

  ```c
  int myIntVar;
  const int MY_INT_CONST;
  ```

## 리터럴(literal)

> 모든 리터럴은 상수이다.

- 숫자 리터럴(정수 리터럴, 실수 리터럴)
- 문자 리터럴
  - 문자 리터럴은 홑따옴표(`'`)로 감싸서 표현한다.
- 문자열 리터럴
  - 문자열 리터럴은 쌍따옴표(`"`)로 감싸서 표현한다.

  ```c
  int myInt = 10;
  double myDouble = 3.14;
  char myChar = 'A';
  char myStringp[] = "Hello";
  ```

## 메크로 상수

<!-- TODO -->
