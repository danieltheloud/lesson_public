# Files 클래스

- `java.nio.file.Files` 클래스는 해당 패키지의 클래스들과 더불어, 파일 및 디렉토리 작업을 간소화하고 효율적으로 처리하기 위한 유틸리티 메소드를 제공한다.
- 이 클래스는 `NIO`(New I/O) 패키지에 포함되어 있으며, 파일 입출력 및 파일 시스템 조작에 유용하다.
- `java.io`보다 대용량 파일 처리에 적합하다.

## 파일 생성, 복사, 이동, 삭제

- 파일 생성
  - `Files.createFile(x)`의 꼴에서 `Path` 인스턴스 `x`의 경로를 포함한 파일명을 기준으로 파일을 생성한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          try {
              Path filePath = Paths.get("example.txt");
              Files.createFile(filePath);
              System.out.println("File created: " + filePath.toAbsolutePath());
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

- 파일 복사
  - `Files.copy(s, t, ...o)`의 꼴에서 원본 파일 `s`를 대상 파일 `t`로 복사하며, 옵션 `o`의 규칙을 적용한다.
  - `StandardCopyOption`
    - `REPLACE_EXISTING` 옵션은 대상 파일이 이미 존재하면 덮어쓰게 한다.
    - `COPY_ATTRIBUTES` 옵션은 원본 파일의 메타 데이터까지 대상 파일로 복사하게 한다.
    - `ATOMIC_MOVE` 옵션은 이동 과정중에 실패할 경우, 중간 상태의 파일을 남기지 않게 한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          try {
              Path source = Paths.get("source.txt");
              Path target = Paths.get("target.txt");
              Files.copy(source, target, StandardCopyOption.REPLACE_EXISTING);
              System.out.println("File copied successfully.");
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

- 파일 이동
  - `Files.move(s, t, o)`의 꼴에서 원본 파일 `s`를 대상 파일 `t`로 이동하며, 옵션 `o`의 규칙을 적용한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          try {
              Path source = Paths.get("source.txt");
              Path target = Paths.get("moved/source.txt");
              Files.move(source, target, StandardCopyOption.REPLACE_EXISTING);
              System.out.println("File moved successfully.");
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

- 파일 삭제
  - `Files.delete(x)`의 꼴에서 파일 `x`를 삭제한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          try {
              Path filePath = Paths.get("example.txt");
              Files.delete(filePath);
              System.out.println("File deleted successfully.");
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

## 파일 읽기, 쓰기

- 파일 쓰기
  - `Files.write(x, i)`의 꼴에서 `Iterable` 인스턴스 `i`의 문자열(`String`) 또는 문자 배열(`char[]`) 요소를 파일 `x`에 한줄씩 작성한다.

  ```java
  import java.nio.file.*;
  import java.util.List;

  public class Main {
      public static void main(String[] args) {
          try {
              Path filePath = Paths.get("example.txt");
              Files.write(filePath, List.of("Hello, World!", "Welcome to Files class."));
              System.out.println("File written successfully.");
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

- 파일 읽기
  - `Files.readAllLines(x)`의 꼴에서 파일 `x`의 모든 문자를 개행을 기준으로 나누어진 문자열들을 `List` 자료형으로 반환한다.

  ```java
  import java.nio.file.*;
  import java.util.List;

  public class Main {
      public static void main(String[] args) {
          try {
              Path filePath = Paths.get("example.txt");
              List<String> lines = Files.readAllLines(filePath);
              lines.forEach(System.out::println);
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

- 스트림을 활용한 파일 처리
  - `Files.lines(x)`의 꼴에서 파일 `x`의 모든 문자를 개행을 기준으로 나누어진 문자열들을 `Stream` 자료형으로 반환한다.
  - 스트림을 활용하면 대용량 파일도 효율적으로 처리할 수 있으며, `람다식`을 통해 간단하게 데이터를 가공하거나 필터링할 수 있다.

  ```java
  import java.nio.file.*;
  import java.util.stream.Stream;

  public class Main {
      public static void main(String[] args) {
          try {
              Path filePath = Paths.get("example.txt");
              Stream<String> lines = Files.lines(filePath);
              lines.forEach(System.out::println);
          } catch (Exception e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

## 파일 확인

- 파일 존재 여부 확인
  - `Files.exists(x)`의 꼴에서 파일 `x`가 존재하는지 여부를 반환한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          Path filePath = Paths.get("example.txt");
          if (Files.exists(filePath)) {
              System.out.println("File exists.");
          } else {
              System.out.println("File does not exist.");
          }
      }
  }
  ```

- 파일 읽기, 쓰기, 실행 가능 여부 확인
  - `Files.isReadable(x)`의 꼴에서 파일 `x`가 읽기 가능한지 여부를 반환한다.
  - `Files.isWritable(x)`의 꼴에서 파일 `x`가 쓰기 가능한지 여부를 반환한다.
  - `Files.isExecutable(x)`의 꼴에서 파일 `x`가 실행 가능한지 여부를 반환한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          Path filePath = Paths.get("example.txt");
          System.out.println("Is readable: " + Files.isReadable(filePath));
          System.out.println("Is writable: " + Files.isWritable(filePath));
          System.out.println("Is executable: " + Files.isExecutable(filePath));
      }
  }
  ```

- 파일 크기 확인
  - `Files.size(x)`의 꼴에서 파일 `x`의 크기를 `byte` 단위로 반환한다.

  ```java
  import java.nio.file.*;

  public class Main {
      public static void main(String[] args) {
          try {
              Path filePath = Paths.get("example.txt");
              long fileSize = Files.size(filePath);
              System.out.println("File size: " + fileSize + " bytes");
          } catch (Exception e) {
              System.out.println("Error occurred while getting file size: " + e.getMessage());
              e.printStackTrace();
          }
      }
  }
  ```
