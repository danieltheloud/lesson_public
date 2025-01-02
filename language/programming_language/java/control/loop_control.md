# 루프 제어문

- `break` 키워드를 사용하면, 반복문이나 `switch`문을 탈출한다.
- `continue` 키워드를 사용하면, 현재 반복의 남은 부분을 건너뛰고 다음 반복으로 진행한다.

## 라벨

- 라벨(label)은 코드 블럭이나 반복문을 식별하기 위한 용도로 사용된다.
- `n : b`의 꼴에서 `n`은 라벨의 이름, `b`는 코드 블럭 또는 반복문이다.
- 라벨을 사용하면 중접 반복문에서 루프 제어문이 어느 반복문에 대해서 작동할지를 지정할 수 있다.
- 라벨을 사용하지 않는다면, 현재의 반복문에 대해서 수행된다.

  ```java
  outer: for (int i = 0; i < 3; i++) {
      for (int j = 0; j < 3; j++) {
          if (j == 1) {
              continue outer; // 외부 반복문의 다음 반복으로 이동
          }
          System.out.println("i: " + i + ", j: " + j);
      }
  }
  ```

  ```java
  outer: for (int i = 0; i < 3; i++) {
      for (int j = 0; j < 3; j++) {
          if (j == 1) {
              break outer; // 외부 반복문을 종료
          }
          System.out.println("i: " + i + ", j: " + j);
      }
  }
  System.out.println("Loop finished");
  ```
