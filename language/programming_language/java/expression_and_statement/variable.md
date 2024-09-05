# 변수와 함수(variable)

## 변수의 선언

- 변수를 선언할 때는 `자료형`, 변수명을 순서대로 나열한다.
  ```java
  // int는 자료형이고, myVar는 변수명이다.
  int myVar;
  ```
- `Java`에는 8가지의 `원시 자료형`(또는 기본형)이 있고, `String`을 포함한 나머지 모든 자료형은 `참조 자료형`(또는 참조형)이다.

### 원시 자료형(primitive type)

- `Java`의 원시 자료형에는 `부호가 없는`(unsigned) 자료형이 따로 존재하지 않는다.

|구분|자료형|기본값|표현 범위|크기|
|:----:|:---:|:---:|:---:|:---:|
|정수형|`byte`|0|-2^7 ~ 2^7-1<br>(-128 ~ 127)|1 byte|
|정수형|`short`|0|-2^15 ~ 2^15-1<br>(-32,768 ~ 32,767)|2 byte|
|정수형|`int`|0|-2,147,483,648 ~ 2,147,483,647<br>(-2^31 ~ 2^31-1)|4 byte|
|정수형|`long`|0L|-9,223,372,036,854,775,808<br>~ 9,223,372,036,854,775,807<br>(-2^63 ~ 2^63-1)|8 byte|
|실수형|`float`|0.0f|1.4E-45 ~ <!-- TODO -->|4 byte|
|실수형|`double`|0.0d|4.9E-324 ~ <!-- TODO -->|8 byte|
|논리형|`boolean`|false|true, false|_가상 머신에 따라 다름_|
|문자형|`char`|'\u0000'|'\u0000'(또는 0)<br>~<br>'\uffff'(또는 65,535)|2 byte|

## 변수 명명법(Name rule)

## 변수의 초기화와 할당

## 변수의 호출

- 변수를 호출할 때는 `자료형`을 생략하고, `변수명`만을 기재한다.