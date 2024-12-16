# 함수형 인터페이스

> 함수형 프로그래밍을 지원하기 위해 `Java 8`에서 도입되었다.

- `함수형 인터페이스`(functional interface)는 **단 하나의 추상 메서드를 가지는 인터페이스**로써, `람다 표현식`이나 `메서드 참조`를 사용하여 구현할 수 있다.
  - `default` 메서드와 `static` 메서드는 포함할 수 있다.
- `@FunctionalInterface` 어노테이션을 사용하여 컴파일러가 `함수형 인터페이스`인지를 확인하도록 명시할 수 있다.

  ```java
  @FunctionalInterface
  interface MyFunction {
      void execute();
  }
  ```
