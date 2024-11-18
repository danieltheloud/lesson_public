# 클래스 정의

- `a class N {}`의 꼴에서 `a`는 접근 제한자, `N`은 클래스의 이름이다.
- **하나의 파일 내에는 하나의 `public` 클래스만 존재해야 함**에 유의한다.
  - 유지보수를 위해서, 하나의 파일에는 하나의 클래스만 작성하는 것이 좋다.
- 명명법: `파스칼 케이스`

  ```java
  public class MyClass {
      // 필드 및 메소드
  }
  ```

## final 클래스

- `a final class N {}`의 꼴에서 `a`는 접근 제한자, `N`은 클래스의 이름이다.
  - `final 클래스`는 다른 클래스가 상속받을 수 없다.

  ```java
  public final class MyClass {
      // 필드 및 메소드
  }
  ```

## 접근 제한자

- `public`: 클래스 외부에서도 접근이 가능하다.
- `protected`: 같은 패키지 내에서 또는 상속 관계에서 접근이 가능하다.
- `default`: 같은 패키지 내에서만 접근이 가능하다.
  - `default`는 직접 작성하는 것이 아닌, **접근 제한자를 생략하는 것임**에 유의한다.
- `private`: 해당 클래스 내에서만 접근이 가능하다.
  - 내부의 정보를 은닉하여 보안성을 높이기 위해서 자주 사용된다.

## 필드

- `a T n;`의 꼴에서 `a`는 접근 제한자, `T`는 자료형, `n`은 변수의 이름이다.
- 필드는 클래스 내에 선언된 변수로, 객체의 속성을 정의한다.
- 명명법: `카멜 케이스`

### 상수 필드

- `a final T n = x;`의 꼴에서 `a`는 접근 제한자, `T`는 자료형, `n`은 변수의 이름이다.
- 상수 필드는 선언과 동시에 초기화해야 한다.
- 명명법: `어퍼 스네이크 케이스`

  ```java
  public class MyClass {
      private final int MY_INT = 10;
  }
  ```

### 인스턴스 필드

- `인스턴스 필드`는 클래스의 **각 인스턴스에 고유하게 존재**하는 필드이다.
- **객체가 생성될 때마다 독립적으로 할당**되며, 인스턴스마다 별도의 값을 갖는다.

  ```java
  public class MyClass {
      private int instInt;
      private String instStr;
  }
  ```

### 정적 필드

- `정적 필드`는 클래스에 하나만 존재하며, **모든 인스턴스가 공유**한다.
- `static` 키워드를 사용하여 선언한다.

  ```java
  public class MyClass {
      private static int staticInt;
      private static String staticStr;
  }
  ```

## 메소드

- `a T n(...x) {}`의 꼴에서 `a`는 접근 제한자, `T`는 반환 타입, `n`은 메소드의 이름, `x`는 매개 변수이다.
  - 반환값이 없다면 `T`에는 `void` 키워드를 사용한다.
- `return` 키워드를 사용하여 특정 값을 반환하게 할 수 있다.
  - 반환 자료형이 `void`인 경우, `return` 키워드를 단독으로 사용하여 메소드를 강제로 종료시킬 수 있다.
- 명명법: `카멜 케이스`

### final 메소드

- `a final T n(...x) {}`의 꼴에서 `a`는 접근 제한자, `T`는 반환 타입, `n`은 메소드의 이름, `x`는 매개 변수이다.
- `final 메소드`는 재정의(overriding)할 수 없다.
- 주로 메소드의 기능을 하위 클래스에서 변경하지 않도록 보장할 때 사용한다.
- `final 메소드`는 보안이나 무결성을 필요로 하는 메소드에 유용하다.
- 성능 최적화 측면에서 `final 메소드`는 `JVM`이 인라인으로 처리할 수 있으므로, 경우에 따라 성능이 향상될 수 있다.

  ```java
  public class MyClass {
      public final void myMethod() {
          System.out.println("This is my method.");
      }
  }
  ```

### 생성자 메소드

- 생성자는 `new` 키워드와 함께 객체가 생성될 때 자동으로 호출되며, **클래스 이름과 동일한 이름**을 가진 메소드로써, 객체 초기화에 사용된다.
  - **반환 자료형은 따로 작성하지 않음**에 유의한다.
- 정의하지 않을 경우, **부모 클래스의 매개 변수가 없는 `생성자`를 암묵적으로 호출하는 `기본 생성자`가 제공**된다.
- 클래스가 명시적으로 부모 클래스를 상속받지 않는다면, `Object` 클래스가 암묵적인 부모 클래스가 된다.

  ```java
  public class MyClass {
      private int instInt;

      public MyClass(int instInt) {
          this.instInt = instInt;
      }
  }
  ```

### 인스턴스 메소드

- `인스턴스 메소드`는 특정 객체의 상태를 조작하거나 반환한다.
- 생성된 인스턴스로부터 `맴버 접근 연산자`를 사용해 호출할 수 있다.

  ```java
  public class MyClass {
      private int instInt;

      public void setInstInt(int instInt) {
          this.instInt = instInt;
      }

      public int getInstInt() {
          return this.instInt;
      }
  }
  ```

### 정적 메소드

- `정적 메소드`는 클래스에 속하며, 클래스 이름으로 직접 호출할 수 있다.
- `인스턴스 필드`에 접근하지 못하며, `정적 필드`나 `정적 메소드`만 사용할 수 있다.
- `static` 키워드를 사용하여 선언한다.

  ```java
  public class MyClass {
      private static String name = "John";

      private static String myStaticFunc1() {
          return String.format("My name is %s.", name);
      }

      public static void myStaticFunc2() {
          System.out.println(myStaticFunc1());
      }
  }
  ```

## getter와 setter 메소드

- `getter`와 `setter` 메소드는 클래스의 `private` 필드에 접근할 수 있도록 제공되는 메소드이다.
- `getter`는 필드의 값을 반환하며, `setter`는 필드의 값을 설정한다.
- 이러한 메소드는 캡슐화 원칙을 준수하면서 객체의 상태를 제어할 수 있게 해준다.
- 명명법: `카멜 케이스`

### getter 메소드

- `getter` 메소드는 `get` 접두사와 필드 이름을 조합하여 이름이 형성되며, 반환값이 존재한다.

  ```java
  public class MyClass {
      private int number;

      // getter 메소드
      public int getNumber() {
          return this.number;
      }
  }
  ```

### setter 메소드

- `setter` 메소드는 `set` 접두사와 필드 이름을 조합하여 이름이 형성되며, 매개 변수를 통해 값을 설정한다.

  ```java
  public class MyClass {
      private int number;

      // setter 메소드
      public void setNumber(int number) {
          this.number = number;
      }
  }
  ```
