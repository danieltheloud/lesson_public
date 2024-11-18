# 클래스 상속

- 클래스 상속(inheritance)은 기존 클래스의 필드와 메소드를 다른 클래스에서 재사용할 수 있도록 해주는 기능이다. 이를 통해 코드의 재사용성을 높이고, 유지보수를 용이하게 만든다.
  - 상속을 하는 클래스를 부모 클래스(parent class) 또는 수퍼 클래스(super class)라고 한다.
  - 상속을 받는 클래스를 자식 클래스(child class) 또는 섭 클래스(sub class)라고 한다.
- `class Sub extends Sup {}`의 꼴에서 클래스 `Sub`는 부모 클래스 `Sup`의 자식 클래스이다.
  - 상속받은 클래스는 부모 클래스의 메소드와 필드를 그대로 사용할 수 있다.
- `Java`는 단일 상속만을 지원한다.
  - 즉, **하나의 클래스는 오직 하나의 부모 클래스만 가질 수 있다**.
- `super` 키워드를 사용하여서 부모 클래스에 접근할 수 있다.
  - `super()`는 부모 클래스의 생성자를 의미한다.

  ```java
  // 부모 클래스
  public class Parent {
      private String name;

      public Parent(String name) {
          this.name = name;
      }

      // 부모 클래스의 메소드
      public void sayMyName() {
          System.out.printf("My name is %s.", this.name));
      }
  }
  ```

  ```java
  // 자식 클래스
  public class Child extends Parent {
      private int age;

      public Child(String name, int age){
          super(name);
          this.age = age;
      }

      // 자식 클래스의 메소드
      public void sayMyAge() {
          System.out.printf("I am %d years old.", this.age));
      }
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          Child child = new Child("John", 10);
          child.sayMyName();  // My name is John.
          child.sayMyAge();   // I am 10 years old.
      }
  }
  ```

## 형변환

- 형변환(casting)에는 업캐스팅(upcasting)과 다운캐스팅(downcasting)이 있다.
- 업캐스팅은 자식 자료형으로 생성된 객체를 부모 자료형 변수에 할당할 때, 자동으로 이루어진다.
  - 업캐스팅은 "자동 형변환"이라고도 부른다.
- 다운캐스팅은 부모 자료형으로 생성된 객체를 자식 자료형 변수에 할당할 때, 수동으로 이루어진다.
  - 다운캐스팅은 "강제 형변환"이라고도 부른다.

## Object 클래스

- `Java`의 모든 클래스는 `Object` 클래스를 상속받는다.
  - `Java`의 모든 객체는 `Object` 자료형으로 사용할 수 있다.

  ```java
  public class Main {
      public static void main(String[] args) throws IOException {
          Object o1 = 10;
          Object o2 = 3.14;
          Object o3 = 'A';
          Object o4 = "Hello, World!";
          Object o5 = new MyClass();
      }
  }
  ```
