# BufferedWriter / BufferedReader 클래스

## BufferedWriter

- `BufferedWriter` 클래스는 텍스트 데이터를 효율적으로 쓰기 위해 사용된다.

  ```java
  import java.io.BufferedWriter;
  import java.io.FileWriter;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try (BufferedWriter bw = new BufferedWriter(new FileWriter("example.txt", true))) {
              bw.write("Appending new text.");
              bw.newLine(); // 줄바꿈
              System.out.println("Successfully wrote to the file.");
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

### BufferedWriter 인스턴스 메소드

- `write`
  - `x.write(s)`의 꼴에서 문자열 `s`을 파일 `x`에 작성한다.
  - `x.write(a, o, l)`의 꼴에서 문자 배열 `a`의 인덱스 `o`부터 최대 길이 `l`만큼 파일 `x`에 작성한다.
- `newLine`
  - `x.newLine()`의 꼴에서 적합한 개행 문자를 파일 `x`에 작성한다.
- `flush`
  - `x.flush()`의 꼴에서 버퍼에 저장된 데이터를 강제로 파일 `x`에 작성한다.
- `close`
  - `x.close()`의 꼴에서 스트림을 닫아 파일 `x`와의 연결을 해제한다.

## BufferedReader

- `BufferedReader` 클래스는 텍스트 데이터를 효율적으로 읽기 위해 사용된다.

  ```java
  import java.io.BufferedReader;
  import java.io.FileReader;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try (BufferedReader br = new BufferedReader(new FileReader("example.txt"))) {
              String line;
              while ((line = br.readLine()) != null) {
                  System.out.println(line);
              }
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

### BufferedReader 인스턴스 메소드

- `read`
  - `x.read()`의 꼴에서 `x`의 한 문자를 읽고 해당 문자의 유니코드 값을 반환한다.
    - 더 이상 읽을 문자가 없으면 `-1`을 반환한다.
  - `x.read(a, o, l)`의 꼴에서 파일 `x`에서 데이터를 읽어 문자 배열 `a`에 인덱스 `o`부터 최대 길이 `l`만큼 기록하고, 읽은 문자 배열의 길이를 반환한다.
- `readLine`
  - `x.readLine()`의 꼴에서 `x`의 한 줄을 읽고 문자열로 반환한다.
    - 더 이상 읽을 줄이 없으면 `null`을 반환한다.
- `close`
  - `x.close()`의 꼴에서 스트림을 닫아 파일 `x`와의 연결을 해제한다.
