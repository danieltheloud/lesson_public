# 변수와 상수(variable and constant)

- 변수와 상수는 어떤 값을 담을 수 있는 일종의 상자와 같다.
- 변수 및 상수의 [명명법](../../../../cs/convention/naming.md)은 카멜 케이스(camel case)를 사용한다.

## 변수와 선언(declaration)

- 변수를 선언할 때는 `var` 또는 `let`이라는 예약어(keyword)와 식별자(identifier)을 순서대로 나열한다.
  ```js
  var myVar1;    // var를 사용하여 변수 myVar1을 선언한다.
  let myVar2;    // let을 사용하여 변수 myVar2를 선언한다.
  ```
  > `var`와 `let`의 차이는 함수에 대한 설명과 함께 살펴본다.

## 변수의 초기화(initialization) 및 할당(assignment)

- 선언된 변수에는 값을 할당할 수 있다.
- 변수에 값을 할당 할 때는 `=` 연산자(operator)를 사용한다.
  ```js
  let myNum;    // 변수 myNum를 선언한다.
  myNum = 10;   // 변수 myNum에 10을 할당한다.
  ```
- 변수를 선언하면서, 동시에 값을 할당하는 것을 초기화라고 한다.
  ```js
  // 변수 initVar를 선언과 동시에 1로 초기화한다.
  let initVar = 1;
  ```

## 상수의 선언 및 초기화

- 상수를 선언할 때는 `const` 예약어와 식별자을 순서대로 나열한다.
- 상수는 선언된 후, 값을 다시 할당할 수 없기 때문에, 꼭 초기화해야 한다.
  ```js
  // const를 사용하여 상수 myMessage를 선언 및 초기화한다.
  const myMessage = 'hi';
  ```
- 상수를 초기화하지 않고, 선언만 하는 경우, 오류(error)가 발생한다.
