# File 클래스

- `File` 클래스는 파일이나 디렉토리의 정보를 관리하는 데 사용된다.

  ```java
  import java.io.File;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          File file = new File("example.txt");

          try {
              if (file.createNewFile()) {
                  System.out.println("File created: " + file.getName());
              } else {
                  System.out.println("File already exists.");
              }
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

## File 스태틱 메소드

- `File.createTempFile`
  - `File.createTempFile(p, s)`의 꼴에서 문자열 `p`를 접두사로, 문자열 `s`를 접미사(확장자)로 사용하여 임시 파일을 생성하여 반환한다.
    - `s`가 `null`일 경우, ".tmp"가 된다.
    - 생성된 임시 파일은 운영체제의 임시 디렉토리에 저장된다.
  - `File.createTempFile(p, s, d)`의 꼴에서 디렉토리인 `File` 객체 `d`를 경로로 생성하여 반환한다.
    - `d`가 `null`일 경우, 생성된 임시 파일은 운영체제의 임시 디렉토리에 저장된다.

## File 인스턴스 메소드

### 파일 속성 확인 메소드

- `canExecute`
  - `x.canExecute()`의 꼴에서 파일 `x`가 실행 가능한지 여부를 반환한다.
- `canRead`
  - `x.canRead()`의 꼴에서 파일 `x`가 실행 가능한지 여부를 반환한다.
- `canWrite`
  - `x.canWrite()`의 꼴에서 파일 `x`가 쓰기 가능한지 여부를 반환한다.
- `exists`
  - `x.exists()`의 꼴에서 파일 또는 디렉토리 `x`가 존재하는지 여부를 반환한다.
- `isDirectory`
  - `x.isDirectory()`의 꼴에서 `x`가 디렉토리인지 여부를 반환한다.
- `isFile`
  - `x.isFile()`의 꼴에서 `x`가 일반 파일인지 여부를 반환한다.

### 파일 생성 메소드

- `createNewFile`
  - `x.createNewFile()`의 꼴에서 파일 `x`를 생성하고, 생성 성공 여부를 반환한다.

### 파일 정보 조회 메소드

- `getAbsolutePath`
  - `x.getAbsolutePath()`의 꼴에서 파일 `x`의 절대 경로를 반환한다.
- `getCanonicalPath`
  - `x.getCanonicalPath()`의 꼴에서 파일 `x`의 표준화된(정규화된) 경로를 반환한다.
    - 심볼릭 링크를 제거하고, 상대 경로를 처리하여 최종적인 경로를 반환한다.
- `getName`
  - `x.getName()`의 꼴에서 파일 `x`의 이름을 반환한다.
- `getPath`
  - `x.getPath()`의 꼴에서 파일 `x`의 경로를 반환한다.
- `lastModified`
  - `x.lastModified()`의 꼴에서 파일 `x`의 마지막 수정 시간을 반환한다.
- `length`
  - `x.length()`의 꼴에서 파일 `x`의 크기를 바이트 단위로 반환한다.

### 디렉토리 생성 메소드

- `mkdir`
  - `x.mkdir()`의 꼴에서 디렉토리 `x`를 생성하고, 생성 성공 여부를 반환한다.
    - 상위 디렉토리가 존재하지 않으면 실패한다.
- `mkdirs`
  - `x.mkdirs()`의 꼴에서 경로의 모든 상위 디렉토리를 포함하여 디렉토리 `x`를 생성하고, 생성 성공 여부를 반환한다.

### 디렉토리 정보 조회 메소드

- `list`
  - `x.list()`의 꼴에서 디렉토리 `x` 내의 파일 및 디렉토리 이름을 문자열 배열(`String[]`)로 반환한다.
- `listFiles`
  - `x.listFiles()`의 꼴에서 디렉토리 `x` 내의 파일 및 디렉토리를 `File` 배열(`File[]`)로 반환한다.

### 파일 및 디렉토리 삭제 메소드

- `delete`
  - `x.delete()`의 꼴에서 파일 또는 디렉토리인 `x`를 삭제하고, 삭제 성공 여부를 반환한다.

### 파일 이름 변경 및 경로 변경

- `renameTo`
  - `x.renameTo(y)`의 꼴에서 파일 또는 디렉토리 `x`의 이름 또는 경로를 `y`로 변경한다.

### 파일 권한 수정

- `setReadOnly`
  - `setReadOnly()`의 꼴에서 파일 `x`를 읽기 전용으로 설정하고, 설정 성공 여부를 반환한다.
- `setWritable`
  - `x.setWritable(b)`의 꼴에서 파일 `x`의 쓰기 권한을 `b`로 설정하고, 설정 성공 여부를 반환한다.
- `setExecutable`
  - `x.setExecutable(b)`의 꼴에서 파일 `x`의 실행 권한을 `b`로 설정하고, 설정 성공 여부를 반환한다.
