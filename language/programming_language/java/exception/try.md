# 예외 처리

- 예외 처리는 `try`문, `catch`문, `finally`문이 사용된다.

## try-catch-finally문

- `try` 블럭에는 예외가 발생할 가능성이 있는 코드를 작성한다.
- `catch` 블럭에는 예외가 발생했을 경우에 실행될 코드를 작성한다.

  ```java
  try {
      // 예외가 발생할 가능성이 있는 코드
  }
  catch (Exception e) {
      // 예외가 발생했을 경우에 실행될 코드
  }
  ```

- `finally` 블럭에는 예외 발생 여부와 상관없이 실행되어야 할 코드가 작성된다.


  ```java
  try {
      // 예외가 발생할 가능성이 있는 코드
  }
  catch (Exception e) {
      // 예외가 발생했을 경우에 실행될 코드
  }
  finally {
      // 예외 발생 여부와 상관없이 실행되어야 할 코드
  }
  ```

## 향상된 try문 (try with resources)

- 향상된 try문은 `AutoCloseable` 인터페이스의 구현체를 받아서 열고, 예외 발생 여부와 상관없이, 자동으로 해당 구현체를 닫는다.

  ```java
  try (AutoCloseable 인스턴스 선언) {
      // 예외가 발생할 가능성이 있는 코드
  }
  catch (Exception e) {
      // 예외가 발생했을 경우에 실행될 코드
  }
  ```
