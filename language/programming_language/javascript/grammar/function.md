# 함수(function)

- `JavaScript`의 함수는 `일급 객체`이다.
  - 함수의 인자로써 함수를 전달할 수 있으며, 이렇게 전달되는 함수를 콜백(`callback`) 함수라고 한다.
  - 함수의 반환 값이 함수일 수 있다.
- 함수는 크게 `내장 함수`와 `사용자 정의 함수`로 분류할 수 있다.

## 내장 함수(built-in function)

- `내장 함수`는 기본적으로 제공되는 함수이다.
- 그러므로 직접 정의(definition)하지 않고도, 호출(call)할 수 있다.

## 사용자 정의 함수(user defined function)

- `사용자 정의 함수`는 개발자가 직접 정의해서 사용하는 함수이다.
- 그러므로 함수를 호출하기 전에 **반드시** 정의가 선행되어야 한다.

## 함수의 정의

- `function f(x) {y}`의 꼴에서 일반 함수(`regular function`)를 정의한다.
  - `f`는 사용자가 정한 함수명이다.
    - 명명법(naming convention)으로는 카멜 케이스(camel case)를 사용한다.
  - 매개변수(parameter) `x`는 선택사항이며, 복수의 매개변수를 가질 수도 있다.
    - 2개 이상의 매개변수를 사용한다면, 매개변수를 쉼표(`,`)로 구분한다.
  - 코드 블럭 `y` 내에서 `return`문은 선택사항이며, `return` 키워드를 뒤따르는 값을 반환한 후에 함수는 즉시 종료된다.

  ```js
  // 매개변수가 없는 함수 func1을 정의한다.
  function func1() {
      console.log("Hello");
  }

  // 매개변수가 3개인 함수 func2를 정의한다.
  function func2(param1, param2, param3) {
      console.log(param1 + param2 + param3);
  }

  func1();                          // Hello
  func2("Hello", ", ", "World!");   // Hello, World!
  ```

- `function (x) {y}`의 꼴에서 익명 함수(`anonymous function`)를 정의한다.
  - 함수명이 없으므로, 함수명을 사용한 호출이 불가능하다.
  - 변수에 대입하여 호출할 수 있다.
    - 다른 함수의 콜백(`callback`) 함수로써, 정의와 동시에 인자로써 넘겨주기 위해서 주로 사용된다.

  ```js
  // 함수 func는 매개변수 callback를 통해서
  // 함수를 인자로 받아서 내부에서 실행한다.
  function func(callback) {
      console.log('함수 시작');
      callback();
      console.log('함수 끝');
  }

  // callback 함수는 함수명으로 호출될 필요가 없으므로
  // 익명 함수로 작성되었다.
  func(function (x) {
      console.log('익명 함수 실행')
  });
  // 함수 시작
  // 익명 함수 실행
  // 함수 끝
  ```

- `(x) => {y}`의 꼴에서 화살표 함수(`arrow function`)을 정의한다.
  - 익명 함수와 마찬가지로 함수명이 존재하지 않는다.
  - 변수가 하나만 존재하는 경우 소괄호(`(`, `)`)는 생략될 수 있다.
  - 코드 블럭 `y`가 하나의 표현식(expression) 또는 명령문(statement)으로만으로 이루어져 있을 때, 중괄호(`{`, `}`)는 생략될 수 있다.
    - 평가된 값은 `return` 키워드를 사용하지 않아도 **자동으로 반환**된다.
  - 익명 함수와는 `this` 키워드의 대상이 다르다.

    > - 이는 `this` 키워드에 대한 설명에서 다시 다룬다.

  ```js
  function func(callback) {
      console.log('함수 시작');
      console.log(callback());
      console.log('함수 끝');
  }

  func((x) => x = 10);
  // 함수 시작
  // 10
  // 함수 끝
  ```
