# 클래스 인스턴스 생성

- 클래스 인스턴스를 생성하는 것은 `객체 지향 프로그래밍`의 핵심으로, 클래스를 기반으로 객체를 생성하여 메모리에 할당하는 과정이다.
- `new` 키워드를 사용하여 클래스의 생성자를 호출함으로써 인스턴스(instance)를 생성할 수 있다.
- `기본 생성자`나 `사용자 정의 생성자`를 사용하여 객체를 초기화할 수 있다.
- 인스턴스를 생성하면 클래스에서 정의한 필드와 메소드를 사용할 수 있게 된다.

  ```java
  public class MyClass {
      private int instInt;

      public MyClass(int instInt) {
          this.instInt = instInt;
      }

      public void myMethod() {
          System.out.println(this.instInt);
      }
  }
  ```

  ```java
  public class MyClass {
      public static void main(String[] args) {
          MyClass myInstance = new MyClass(10);
          myInstance.myMethod();  // 10
      }
  }
  ```
