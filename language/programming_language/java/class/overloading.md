# 메소드 오버로딩

- `메소드 오버로딩`(overloading)은 **동일한 이름**의 메소드를 여러 개 정의하되, **매개 변수의 자료형이나 개수**를 다르게 지정하는 것을 말한다.
  - **반환 자료형만 다르고 매개 변수는 동일할 경우**에는 오버로딩으로 간주되지 않음에 유의한다.

  ```java
  public class MyClass {
      static void func(String x) {
          System.out.println("x : ".concat(x));
      }
      static void func(String x, String y) {
          System.out.println(String.format("%s, %s!", x, y));
      }

      public static void main(String[] args) throws IOException {
          func("Hello");          // x : Hello
          func("Hello", "World"); // Hello, World!
      }
  }
  ```

## 생성자 메소드 오버라이딩

- `생성자 메소드 오버로딩`은 클래스의 생성자를 여러 개 정의하되, 매개 변수의 자료형이나 개수가 다르게 하여 다양한 방법으로 객체를 초기화할 수 있도록 하는 기능이다.

  ```java
  public class MyClass {
      private String name;
      private int age;

      // 기본 생성자 (매개 변수가 없음)
      public MyClass() {
          this.name = "Unknown";
          this.age = 0;
      }

      // 매개 변수가 하나인 생성자
      public MyClass(String name) {
          this.name = name;
          this.age = 0;
      }

      // 매개 변수가 두 개인 생성자
      public MyClass(String name, int age) {
          this.name = name;
          this.age = age;
      }

      public void displayInfo() {
          System.out.println("Name: " + this.name + ", Age: " + this.age);
      }

      public static void main(String[] args) {
          MyClass obj1 = new MyClass();
          MyClass obj2 = new MyClass("Alice");
          MyClass obj3 = new MyClass("Bob", 25);

          obj1.displayInfo(); // Name: Unknown, Age: 0
          obj2.displayInfo(); // Name: Alice, Age: 0
          obj3.displayInfo(); // Name: Bob, Age: 25
      }
  }
  ```

  - 오버로딩된 생성자 간에 중복되는 코드가 많을 경우, 코드의 유지보수를 위해 `this()`를 사용하여 다른 생성자를 호출하는 방식으로 중복을 줄일 수 있다.

  ```java
  public class MyClass {
      private String name;
      private int age;

      public MyClass() {
          this("Unknown", 0); // 다른 생성자를 호출하여 초기화
      }

      public MyClass(String name) {
          this(name, 0);  // 두 번째 생성자를 호출하여 초기화
      }

      public MyClass(String name, int age) {
          this.name = name;
          this.age = age;
      }
  }
  ```
