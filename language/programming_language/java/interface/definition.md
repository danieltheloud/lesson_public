# 인터페이스 정의

- `A interface n {}`의 꼴에서 `A`는 접근 제한자, `n`은 인터페이스의 이름이다.
- 인터페이스에 선언된 모든 필드는 기본적으로 `public static final`이다.
- 인터페이스에 선언된 모든 메소드는 기본적으로 `public` 및 `abstract`이다.

  ```java
  public interface MyInterface {
      int MY_NUMBER = 10;
      void myFunc();
  }
  ```

## 디폴트 메소드

- `Java 8`부터 인터페이스 내에서 `default` 키워드를 사용하여 디폴트 메소드를 정의할 수 있다.
- 디폴트 메소드는 인터페이스를 구현하는 클래스에 구현을 강제하지 않고, 선택적으로 재정의할 수 있는 메소드이다.
- 기존 코드와의 호환성을 유지하면서 새로운 기능을 추가할 수 있도록 돕는다.

  ```java
  public interface MyInterface {
      void abstractMethod();  // 추상 메소드

      default void defaultMethod() {
          System.out.println("This is a default method in the interface.");
      }
  }
  ```

  ```java
  public class MyClass implements MyInterface {
      @Override
      public void abstractMethod() {
          System.out.println("Implementation of the abstract method.");
      }

      // defaultMethod()는 재정의하지 않아도 자동으로 사용 가능
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          MyClass obj = new MyClass();
          obj.abstractMethod(); // Implementation of the abstract method.
          obj.defaultMethod();  // This is a default method in the interface.
      }
  }
  ```

## 정적 메소드

- `Java 8`부터 인터페이스 내에 `static` 키워드를 사용하여 정적 메소드를 정의할 수 있다.
- 정적 메소드는 클래스 인스턴스 없이, 인터페이스 이름을 통해 직접 호출할 수 있다.
- 인터페이스와 관련된 유틸리티 메소드를 제공할 때 유용하다.

  ```java
  public interface MyInterface {
      static void staticMethod() {
          System.out.println("This is a static method in the interface.");
      }
  }

  public class Main {
      public static void main(String[] args) {
          // 인터페이스 이름을 통해 직접 호출
          MyInterface.staticMethod(); // This is a static method in the interface.
      }
  }
  ```
