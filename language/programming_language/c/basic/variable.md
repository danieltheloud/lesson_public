# 변수와 상수

- 변수는 메모리(memory)의 특정 주소(address)를 가리키는 식별자(identifier)이다.
- 식별자는 영어 대소문자, 숫자, 언더바(_)를 포함할 수 있다.

## 변수

- 변수(variable)는 값이 변할 수 있는 수이다.
- 명명법: `카멜 케이스`

  ```c
  int myIntVar;
  ```

## 상수

- 상수(constant)는 값이 변할 수 없는 수이다.

### 심볼릭 상수

- `const` 키워드를 사용하여서, 심볼릭(symbolic) 상수는 선언할 수 있다.
- 명명법: `어퍼 스네이크 케이스`

  ```c
    const int MY_INT_CONST;
  ```

### 리터럴 상수

> 모든 리터럴(literal)은 상수이다.

- 숫자 리터럴(정수 리터럴, 실수 리터럴)
- 문자 리터럴
  - 문자 리터럴은 홑따옴표(`'`)로 감싸서 표현한다.
- 문자열 리터럴
  - 문자열 리터럴은 쌍따옴표(`"`)로 감싸서 표현한다.

  ```c
  int myInt = 10;
  double myDouble = 3.14;
  char myChar = 'A';
  char myString[] = "Hello";
  ```

### 메크로 상수

- 메크로(macro) 상수는 전처리기를 통해서 정의된 상수이다.
- 식별자처럼 사용할 수 있지만, 실체는 리터럴이다.

<!-- TODO -->

### 배열 상수

- 배열(array)의 식별자는 해당 배열의 첫번째 요소(element)에 해당하는 주소 상수이다.

<!-- TODO -->
