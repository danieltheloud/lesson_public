# 객체(object)

- 객체는 JavaScript의 핵심적인 자료형이다.
- `C++`나 `Java`의 `Map`, `Python`의 `dictionary` 자료형과 유사하게, 키(key)와 값(value)의 쌍으로써 속성(property)를 가진다.

## 객체의 선언(declaration) 및 초기화(initialization)

- 객체 리터럴(literal)에 의한 선언 및 초기화

  > - 객체를 리터럴로 표현할 때는, 중괄호(`{`, `}`)로 감싸준다.
  > - 속성은 키와 값으로 이루어져 있으며, 키와 값을 콜론(`:`)으로 구분한다.
  > - 각 속성은 콤마(`,`)로 구분한다.
  >
  >   ```js
  >   let myObject = {
  >       name: '홍길동',
  >       age: 18,
  >       hobby: 'coding'
  >   }
  >   ```

- 생성자(constructor)에 의한 선언 및 초기화

<!-- TODO -->
