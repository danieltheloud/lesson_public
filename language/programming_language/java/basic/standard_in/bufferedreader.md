# BufferedReader 클래스

- `BufferedReader`는 `java.io` 패키지에 포함되어 있으며, 대량의 데이터를 처리하거나 속도가 중요한 경우 유용하다.

  ```java
  import java.io.BufferedReader;
  import java.io.InputStreamReader;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) throws IOException {
          BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

          // 문자열 입력
          System.out.print("Enter a string: ");
          String str = br.readLine();

          // 정수 입력
          System.out.print("Enter an integer: ");
          int num = Integer.parseInt(br.readLine());

          System.out.println("String: " + str);
          System.out.println("Integer: " + num);

          // 입력 스트림 닫기
          br.close();
      }
  }
  ```

## BufferedReader 인스턴스 메소드

- `read`
  - `x.read()`의 꼴에서 문자(character) 하나를 입력받아서 정수(ASCII 코드)로 반환한다.
  - `x.read(a)`의 꼴에서 문자 배열 `a`에 해당 배열의 크기 이하의 문자들를 입력받아서 저장하고, 읽은 문자 수를 반환한다.
  - `x.read(a, o, l)`의 꼴에서 배열 `a`의 인덱스 `o`부터 최대 `l` 길이만큼의 문자들을 입력받아서 저장하고, 읽은 문자 수를 반환한다.
- `readLine`
  - `x.readLine()`의 꼴에서 한 줄의 문자열을 입력받아 반환한다.
- `close`
  - `x.close()`의 꼴에서 `x`의 입력 스트림을 닫아줌으로써, 메모리 누수 등의 문제를 방지한다.
