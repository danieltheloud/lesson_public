# 제네릭

- 제네릭(generic)은 클래스나 메소드에서 사용할 자료형을 지정하지 않고, 다양한 자료형의 객체를 처리할 수 있도록 지원하는 기능이다.
- 컴파일 시점에 타입 체크가 이루어지므로, 런타임 오류를 줄일 수 있다.
- 같은 기능을 수행하는 코드가 여러 자료형을 처리할 수 있으므로, 코드 중복을 줄일 수 있다.
- 제네릭을 사용하면 코드가 더 읽기 쉬워지고, 반환 자료형과 타입 파라미터를 명확히 알 수 있다.
- 제네릭에는 원시 자료형을 사용할 수 없으므로, 필요하다면 래퍼 클래스를 사용해야 한다.

## 제네릭 클래스

- `a class N<T>`의 꼴에서 `a`는 접근 제한자, `N`은 클래스의 이름, `T`는 타입 파라미터이다.

  ```java
  public class MyClass<T> {
      private T content;

      public void setContent(T content) {
          this.content = content;
      }

      public T getContent() {
          return this.content;
      }
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) throws IOException {
          MyClass<String> stringInstance = new MyClass<>();
          stringInstance.setContent("Hello");
          System.out.println(stringInstance.getContent());    // Hello

          MyClass<Integer> intInstance = new MyClass<>();
          intInstance.setContent(10);
          System.out.println(intInstance.getContent());       // 10
      }
  }
  ```

## 제네릭 메소드

- `a <T> T n(...x)`의 꼴에서 `a`는 접근 제한자, `<T>`는 타입 파라미터, `T`는 반환 자료형, `n`은 메소드의 이름, `x`는 매개 변수이다.
- 정적 메소드의 경우, `a static <T> T n(...x)`의 꼴로 작성한다.

  ```java
  public class MyClass {
      public static <T> void printArray(T[] array) {
          for (T element : array) {
              System.out.print(element + " ");
          }
          System.out.println();
      }
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) throws IOException {
          Integer[] array = {10, 20, 30, 40, 50};
          MyClass.printArray(array);  // 10 20 30 40 50
      }
  }
  ```

## 제네릭 와일드 카드

- `?` : 제한 없는 와일드카드
  - 어떤 타입이든 허용한다.
  - 객체의 타입에 관계없이 데이터를 읽을 때 유용하다.
  - 데이터를 추가하는 작업은 불가능하다.
- `? extends T` : 상한 제한 와일드카드
  - T 타입 또는 그 하위 타입만 허용한다.
  - 데이터를 읽을 수는 있지만 추가 작업은 제한된다.
  - 데이터를 읽기만 해야 하는 경우 사용한다.
- `? super T` : 하한 제한 와일드카드
  - T 타입 또는 그 상위 타입만 허용한다.
  - 데이터를 추가할 수 있지만, 읽을 때는 Object로 반환된다.
  - 데이터를 추가해야 하는 경우 사용한다.

<!-- TODO -->
