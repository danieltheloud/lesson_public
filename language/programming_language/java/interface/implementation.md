# 인터페이스 구현

- `A class n implements i {}`의 꼴에서 클래스 `n`는 인터페이스 `i`의 모든 메소드를 구현해야 한다.

  ```java
  public interface MyInterface {
      void hello();
  }
  ```

  ```java
  public class MyClass implements MyInterface {
      @Override
      public void hello() {
          System.out.println("Hello, World!");
      }
  }
  ```

- 클래스는 하나 밖에 상속받지 못하지만, 여러 인터페이스를 구현할 수는 있다.
- 여러 인터페이스를 구현하려면, 쉼표로 구분하여 나열한다.

  ```java
  public interface MyInterface1 {
      void hello();
  }
  ```

  ```java
  public interface MyInterface2 {
      void bye();
  }
  ```

  ```java
  public class MyClass implements MyInterface1, MyInterface2 {
      @Override
      public void hello() {
          System.out.println("Hello, World!");
      }

      @Override
      public void bye() {
          System.out.println("Good bye, World!");
      }
  }
  ```
