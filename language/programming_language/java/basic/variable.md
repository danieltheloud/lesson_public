# 변수

- 변수(variable)는 값을 담을 수 있는 일종의 상자이다.
- 명명법: `카멜 케이스`

  ```txt
  thisIsMyIntiable
  ```

## 상수

- 상수는 변하지 않는 값을 갖는다.
- 명명법: `어퍼 스네이크 케이스`

  ```java
  THIS_IS_MY_VARIABLE
  ```

## 변수의 선언(definition)

- 변수를 선언할 때는 `자료형`, 변수명을 순서대로 나열한다.

  ```java
  // int는 자료형이고, myInt는 변수명이다.
  int myInt;
  ```

> `Java`에는 8가지의 `원시 자료형`(또는 기본형)이 있고, `String`을 포함한 나머지 모든 자료형은 `참조 자료형`(또는 참조형)이다.

## 변수의 초기화(initialization)와 할당(assignment)

- 변수의 할당은 이미 선언된 변수에 값을 넣는 것이다.

  ```java
  int myInt;  // 변수 myInt를 선언한다.
  myInt = 1;  // myInt에 1을 할당한다.
  ```

- 변수의 선언과 동시에 값을 할당하는 것을 초기화라고 한다.
- 상수는 선언과 동시에 초기화해야만 한다.
- 상수를 선언 및 초기화할 때는 `final` 키워드를 앞에 붙여준다.

  ```java
  int myInt = 1;          // 변수 myInt를 1으로 초기화한다.
  final int MY_INT = 0;   // 상수 MY_INT를 0으로 초기화한다.
  ```

## 변수의 호출(call)

- 변수를 호출할 때는 `자료형`을 생략하고, `변수명`만을 기재한다.

  ```java
  int myInt = 10;
  System.out.println(myInt);
  ```
