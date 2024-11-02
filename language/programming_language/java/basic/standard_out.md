# 기본 출력 함수

- `System.out.print()`
  - `System.out.print(x)`의 꼴에서 `x`를 출력한다.

  ```java
  System.out.print("Hello, World!");
  ```

  ```java
  Hello, World! // <- 출력 후, 줄이 바뀌지 않는다.
  ```

- `System.out.println()`
  - `System.out.println(x)`의 꼴에서 `x`를 출력하고 개행한다.

  ```java
  System.out.print("Hello, World!");
  ```

  ```java
  Hello, World!
  // <- 출력 후, 줄이 바뀐다.
  ```

- `System.out.printf()`
  - `System.out.print(x, y)`의 꼴에서 `x`의 서식 문자에 `y`를 대입하여 출력한다.

  ```java
  System.out.printf("Hello, %s", "World!");
  ```

  ```java
  Hello, World! // <- 출력 후, 줄이 바뀌지 않는다.
  ```
