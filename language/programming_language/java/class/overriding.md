# 메소드 오버라이딩

- 상속받은 메소드를 하위 클래스에서 재정의하는 것을 오버라이딩(overriding)이라고 한다.
- 오버라이딩할 때는 메소드의 이름과 매개 변수가 부모 클래스의 메소드와 정확히 같아야 한다.
- `@Override` 어노테이션을 사용하여 컴파일러가 올바른 오버라이딩인지 확인할 수 있다.

  ```java
  // 부모 클래스
  public class Parent {
      public void hello() {
          System.out.println("Hello, World!");
      }
  }
  ```

  ```java
  // 자식 클래스
  public class Child extends Parent {
      // 부모 클래스의 메소드를 재정의한다.
      @Override
      public void hello() {
          System.out.println("Hi there!");
      }
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          Child child = new Child();
          child.hello();  // Hi there!
      }
  }
  ```
