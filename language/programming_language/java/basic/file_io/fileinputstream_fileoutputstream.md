# FileInputStream / FileOutputStream 클래스

- `FileInputStream`와 `FileOutputStream` 클래스는 바이트 단위로 데이터를 읽고 쓰기 위해서 사용된다.
- 주로 이미지, 동영상 등의 바이너리 파일을 처리하는 데 적합하다.

## FileInputStream

- `FileInputStream` 클래스는 바이너리 데이터를 효율적으로 읽기 위해 사용된다.

  ```java
  import java.io.FileInputStream;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try (FileInputStream fis = new FileInputStream("example.bin")) {
              int data;
              while ((data = fis.read()) != -1) {
                  System.out.print((char) data);
              }
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

### FileInputStream 인스턴스 메소드

- `read`
  - `x.read()`의 꼴에서 파일에서 한 바이트를 읽고 해당 값을 반환한다.
    - 더 이상 읽을 데이터가 없으면 `-1`을 반환한다.
  - `x.read(a, o, l)`의 꼴에서 파일 `x`에서 바이트 배열 `a`의 인덱스 `o`부터 최대 길이 `l`만큼 바이트를 읽어서 기록하고, 읽은 바이트의 길이를 반환한다.
- `available`
  - `x.available()`의 꼴에서 파일 `x`로부터 읽을 수 있는 바이트 수를 반환한다.
- `close`
  - `x.close()`의 꼴에서 스트림을 닫아 파일 `x`와의 연결을 해제한다.

## FileOutputStream

- `FileOutputStream` 클래스는 바이너리 데이터를 효율적으로 쓰기 위해 사용된다.

  ```java
  import java.io.FileOutputStream;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try (FileOutputStream fos = new FileOutputStream("example.bin")) {
              fos.write(new byte[]{65, 66, 67}); // ASCII 코드로 A, B, C
              System.out.println("Data written successfully.");
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

### FileOutputStream 인스턴스 메소드

- `write`
  - `x.write(y)`의 꼴에서 정수(int) 또는 바이트 배열(`byte[]`) `y`를 파일 `x`에 쓴다.
  - `x.write(a, o, l)`의 꼴에서 바이트 배열 `a`의 인덱스 `o`부터 최대 길이 `l`만큼 파일 `x`에 쓴다.
- `flush`
  - `x.flush()`의 꼴에서 버퍼에 저장된 데이터를 강제로 파일 `x`에 쓴다.
- `close`
  - `x.close()`의 꼴에서 스트림을 닫아 파일 `x`와의 연결을 해제한다.
