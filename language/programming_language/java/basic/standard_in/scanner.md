# Scanner 클래스

- `Scanner` 클래스는 `java.util` 패키지에 포함되어 있으며, 입력을 읽기 쉽게 처리할 수 있는 가장 일반적인 방법 중 하나이다.

  ```java
  import java.util.Scanner;

  public class Main {
      public static void main(String[] args) {
          Scanner scanner = new Scanner(System.in);

          // 문자열 입력
          System.out.print("Enter a string: ");
          String str = scanner.nextLine();

          // 정수 입력
          System.out.print("Enter an integer: ");
          int num = scanner.nextInt();

          // 실수 입력
          System.out.print("Enter a double: ");
          double dbl = scanner.nextDouble();

          System.out.println("String: " + str);
          System.out.println("Integer: " + num);
          System.out.println("Double: " + dbl);

          scanner.close(); // 입력 스트림 닫기
      }
  }
  ```

## Scanner 인스턴스 메소드

- `next`
  - `x.next()`의 꼴에서 **공백(space)이나 개행(new line)까지**의 하나의 단어를 입력받아서 반환한다.
  - `x.nextByte()`의 꼴에서 `byte`(정수) 값을 입력받아서 반환한다.
  - `x.nextShort()`의 꼴에서 `short`(정수) 값을 입력받아서 반환한다.
  - `x.nextInt()`의 꼴에서 `int`(정수) 값을 입력받아서 반환한다.
  - `x.nextLong()`의 꼴에서 `long`(정수) 값을 입력받아서 반환한다.
  - `x.nextFloat()`의 꼴에서 `float`(실수) 값을 입력받아서 반환한다.
  - `x.nextDouble()`의 꼴에서 `double`(실수) 값을 입력받아서 반환한다.
  - `x.nextBoolean()`의 꼴에서 `boolean`(논리) 값을 입력받아서 반환한다.
- `nextLine`
  - `x.nextLine()`의 꼴에서 **개행까지**의 모든 문자열을 입력받아서 반환한다.
- `close`
  - `x.close()`의 꼴에서 `x`의 입력 스트림을 닫아줌으로써, 메모리 누수 등의 문제를 방지한다.

## 주의 사항

- `next` 계열의 메소드를 실행한 후에 `nextLine` 메소드 사용하면, 앞선 입력에서 남은 개행 문자를 처리하지 못해서 문제가 발생할 수 있다.
  - `nextLine`을 한번 호출해서 남은 개행 문자를 제거한 후에, 다시 `nextLine` 메소드를 호출함으로써, 문제를 해결할 수 있다.
