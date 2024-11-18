# 값에 의한 호출과 참조에 의한 호출

- 프로그래밍 언어에서 함수를 호출할 때, 함수로 전달되는 인자가 함수 내부에서 어떻게 처리되는지에 따라 **값에 의한 호출**(call by value)과 **참조에 의한 호출**(call by reference)로 나뉜다.
- 이 두 가지 호출 방식은 인자가 함수 내부에서 어떻게 다루어지는지를 결정하며, 프로그램의 동작 방식에 큰 영향을 미친다.

## 값에 의한 호출

- 값에 의한 호출은 **인자의 복사본**을 함수에 전달하는 방식이다.
  - 원시 자료형의 인자는 값에 복사하여 매개 변수에 할당한다.
  - 함수 내에서 인자의 값을 변경해도, **원본 데이터는 변경되지 않음**에 유의한다.

  ```java
  public class CallByValueExample {
      public static void modifyValue(int x) {
          x = 20; // 매개 변수 x는 인자를 복사한 값이므로, 원본은 수정되지 않는다.
      }

      public static void main(String[] args) {
          int num = 10;
          modifyValue(num);
          System.out.println(num);    // 10
      }
  }
  ```

## 참조에 의한 호출

- 인자의 참조(주소)를 함수에 전달하는 방식이다.
  - 참조 자료형의 인자는 참조(메모리 주소)를 복사하여 매개 변수에 할당한다.
  - 함수 내에서 인자의 값을 변경하면, **원본 데이터가 변경됨**에 유의한다.

  ```java
  public class CallByReferenceExample {
      public static void modifyArray(int[] arr) {
          arr[0] = 100;   // 원본 배열의 첫 번째 요소가 변경됨
      }

      public static void main(String[] args) {
          int[] numbers = {10, 20, 30};
          modifyArray(numbers);
          System.out.println(numbers[0]); // 100
      }
  }
  ```

- **매개 변수의 참조(메모리 주소)가 바뀌면 원본이 수정되지 않음**에 유의한다.

  ```java
  public class CallByReferenceExample {
      public static void modifyArray(String str) {
          str = "Bye";   // 참조가 바뀌므로, 원본은 수정되지 않는다.
      }

      public static void main(String[] args) {
          String str = "Hi";
          modifyArray(str);
          System.out.println(str);    // Hi
      }
  }
  ```
