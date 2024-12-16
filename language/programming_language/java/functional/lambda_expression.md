# 람다 표현식

- `람다 표현식`(lambda expression)은 `익명 함수`를 작성하기 위한 간결한 문법이다.
- `람다 표현식`을 사용해서 `함수형 인터페이스`의 추상 메소드를 구현하며, 코드의 간결성과 가독성을 높인다.
- `(...x) -> {...y}`의 꼴에서 `x`는 매개 변수, `y`는 실행될 구문이다.
  - 매개변수 `x`가 하나 뿐이라면, 소괄호(`(`, `)`)는 생략할 수 있다.
  - 구문 `y`가 하나 뿐이거나 단일 표현식이라면, 중괄호(`{`, `}`)는 생략할 수 있다.

  ```java
  @FunctionalInterface
  interface Greeting {
      void sayHello(String name);
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          // 람다 표현식으로 함수형 인터페이스 구현
          Greeting greeting = name -> System.out.println("Hello, " + name);
          greeting.sayHello("John");
      }
  }
  ```

- **`람다 표현식` 내부에서 사용되는 `this` 키워드는, `람다 표현식`이 정의한 외부 클래스의 인스턴스를 참조함**에 유의한다.

  ```java
  @FunctionalInterface
  interface Greeting {
      void sayHello(String name);
  }
  ```

  ```java
  public class Main {
      private String message = "Outer class message";

      public void demonstrateThis() {
          Greeting greeting = name -> {
              System.out.println("Hello, " + name);
              System.out.println("Message from outer class: " + this.message);
          };

          greeting.sayHello("Alice");
      }

      public static void main(String[] args) {
          Main main = new Main();
          main.demonstrateThis();
      }
  }
  ```
