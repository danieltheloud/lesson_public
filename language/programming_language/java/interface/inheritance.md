# 인터페이스 상속

- 인터페이스끼리의 상속은 하나의 인터페이스가 다른 인터페이스를 확장해서 기능을 추가하거나 결합하는 기능을 제공한다.
- 인터페이스끼리의 상속에서는 `extends` 키워드를 사용한다.
- 클래스 상속과는 달리, 인터페이스는 다중 상속을 지원한다.

  ```java
  interface A {
      void a();
  }
  ```

  ```java
  interface B {
      void b();
  }
  ```

  ```java
  // 다중 상속을 통해 확장된 인터페이스
  interface C extends A, B {
      void c();
  }
  ```

  ```java
  // 인터페이스를 구현하는 클래스
  class D implements C {
      @Override
      public void a() {
          System.out.println("D's a\n");
      }

      @Override
      public void b() {
          System.out.println("D's b\n");
      }

      @Override
      public void c() {
          System.out.println("D's c\n");
      }
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          D d = new D();
          d.a();  // D's a
          d.b();  // D's b
          d.c();  // D's c
      }
  }
  ```
