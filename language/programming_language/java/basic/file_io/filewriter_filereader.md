# FileWriter / FileReader 클래스

## FileWriter

- `FileWriter` 클래스는 파일에 데이터를 쓰기 위해서 사용된다.
- `FileWriter` 인스턴스는 기본적으로 파일을 덮어쓴다.
- 파일에 내용을 추가하려면 생성자에서 `append` 모드를 활성화해야 한다.
  - `append` 모드를 활성화하려면 생성자의 두번째 인자를 `true`로 준다.
  - 두번째 인자를 주지 않으면 `false`로 취급된다.

  ```java
  import java.io.FileWriter;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try (FileWriter writer = new FileWriter("example.txt", true)) {
              writer.write("Hello, File I/O in Java!");
              System.out.println("Successfully wrote to the file.");
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

### FileWriter 인스턴스 메소드

- `write`
  - `x.write(y)`의 꼴에서 문자열(`String`) 또는 문자 배열(`char[]`) `y`를 파일 `x`에 작성한다.
  - `x.append(y)`와 같다.
- `flush`
  - `x.flush()`의 꼴에서 버퍼에 남아 있는 데이터를 강제로 파일 `x`에 작성한다.
- `close`
  - `x.close()`의 꼴에서 스트림을 닫아 파일 `x`와의 연결을 해제한다.

## FileReader

- `FileReader` 클래스는 파일에 데이터를 읽기 위해서 사용된다.
- `FileReader` 인스턴스는 데이터를 문자 기반으로 읽으므로 텍스트 파일에 적합하다.
- 파일이 존재하지 않을 경우 `FileNotFoundException`을 던진다.

  ```java
  import java.io.FileReader;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try (FileReader reader = new FileReader("example.txt")) {
              int character;
              while ((character = reader.read()) != -1) {
                  System.out.print((char) character);
              }
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

### FileReader 인스턴스 메소드

- `read`
  - `x.read()`의 꼴에서 파일 `x`에서 한 문자를 읽고 정수(Unicode)를 반환한다.
    - 파일 끝에 도달하면 `-1`을 반환한다.
  - `x.read(a)`의 꼴에서 파일 `x`에서 데이터를 읽어 문자 배열 `a`에 기록한다.
    - 읽은 문자 수를 반환하며, 파일 끝에 도달하면 `-1`을 반환한다.
  - `x.read(a, o, l)`의 꼴에서 파일 `x`에서 데이터를 읽어 문자 배열 `a`에 인덱스 `o`부터 길이 `l`만큼 기록한다.
- `close`
  - `x.close()`의 꼴에서 스트림을 닫아 파일 `x`와의 연결을 해제한다.
