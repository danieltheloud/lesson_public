# 더블 콜론 연산자

- `더블 콜론 연산자`(double colon)는 **메서드 참조**(method reference)에 사용된다.
- `람다 표현식`을 대신해서 기존에 정의된 메소드를 사용하기 위해서 사용된다.

## 생성자 참조

- `C::new`의 꼴에서 `C`는 클래스의 이름이다.
- 해당 클래스의 생성자를 호출한다.

  ```java

  @FunctionalInterface
  interface MyInterface<T> {
      T[] makeArray(int size);
  }
  ```

  ```java
  import java.util.Arrays;
  public class Main {
      public static void main(String[] args) {
          // 람다 표현식으로 배열 생성
          MyInterface<String> myLambda = x -> new String[x];

          // 생성자 참조로 배열 생성
          MyInterface<String> myReference = String[]::new;

          // 람다 표현식 사용
          String[] lambdaResult = myLambda.makeArray(2);
          Arrays.fill(lambdaResult, "hello");
          System.out.println(Arrays.toString(lambdaResult));

          // 생성자 참조 사용
          String[] referenceResult = myReference.makeArray(4);
          Arrays.fill(referenceResult, "world");
          System.out.println(Arrays.toString(referenceResult));
      }
  }
  ```

## 정적 메서드 참조

- `C::m`의 꼴에서 `C`는 클래스의 이름, `m`은 메소드의 이름이다.

  ```java
  @FunctionalInterface
  interface MyInterface {
      int intParser(String x);
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          // 람다 표현식으로 배열 생성
          MyInterface myLambda = x -> Integer.valueOf(x);

          // 생성자 참조로 배열 생성
          MyInterface myReference = Integer::valueOf;

          // 람다 표현식 사용
          int a = myLambda.intParser("10");

          // 생성자 참조 사용
          int b = myReference.intParser("20");

          System.out.printf("a = %d\nb = %d\n", a, b);
      }
  }
  ```

## 인스턴스 메서드 참조

- `C::m`의 꼴에서 `C`는 클래스의 이름, `m`은 메소드의 이름이다.
  - **추상 메소드의 첫번째 인자로써 인스턴스를 넘겨줌에 유의**한다.

  ```java
  @FunctionalInterface
  interface MyInterface {
      boolean compare(String x, String y);
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          // 람다 표현식으로 구현
          MyInterface myLambda = (x, y) -> x.equals(y);

          // 인스턴스 메서드 참조로 구현
          MyInterface myReference = String::equals;

          // 람다 표현식 사용
          System.out.println(myLambda.compare("Hello", "World"));

          // 메서드 참조 사용
          System.out.println(myReference.compare("Hello", "Hello"));
      }
  }
  ```

## 특정 객체의 메서드 참조

- `i::m`의 꼴에서 `i`는 인스턴스의 이름, `m`은 메소드의 이름이다.

  ```java
  class MyClass {
      private String name;

      public MyClass(String name) {
          this.name = name;
      }

      public void sayMyName() {
          System.out.printf("My name is %s.\n", this.name);
      }
  }
  ```

  ```java
  @FunctionalInterface
  interface MyInterface {
      void say();
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) {
          MyClass mc = new MyClass("John");

          MyInterface myLambda = () -> System.out.println("My name is John");
          MyInterface myReference = mc::sayMyName;

          myLambda.say();
          myReference.say();
      }
  }
  ```
