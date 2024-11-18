# 조건문

- 조건문(conditional)은 특정 조건에 따라 코드의 실행 흐름을 제어하기 위해서 사용된다.

## if문

> if문은 조건이 참일 때 특정 코드를 실행한다.

- `if`문은 `if`, `else if`, `else` 구문으로 구성되며, `if`를 제외한 나머지 구문은 선택사항이다.
  - `if (c) {x}`의 꼴에서 조건식 `c`가 참이면, 스코프 `x`를 실행한다.
  - `else if (c) {x}`의 꼴에서 조건식 `c`가 참이면, 스코프 `x`를 실행한다.
  - `else {x}`의 꼴에서 앞선 모든 조건이 거짓이면, 스코프 `x`를 실행한다.

  ```java
  int score = 85;

  if (score >= 90) {
      System.out.println("A학점");
  } else if (score >= 80) {
      System.out.println("B학점");
  } else {
      System.out.println("C학점");
  }
  ```

## switch문

> switch문은 변수 값에 따라 여러 경우(case) 중 하나를 선택하여 실행한다.

- `switch`문은 표현식의 값과 일치하는 `case`를 찾아 해당 블록을 실행한다.
- `default` 블록을 추가하여 어떠한 `case`와도 일치하지 않을 때의 실행 코드를 정의할 수 있다.
- 각 `case`에는 `break` 문을 사용하여 블록 실행 후 `switch`문을 빠져나간다.

    ```java
    int day = 3;

    switch (day) {
        case 0:
            System.out.println("일요일");
            break;
        case 1:
            System.out.println("월요일");
            break;
        case 2:
            System.out.println("화요일");
            break;
        case 3:
            System.out.println("수요일");
            break;
        case 4:
            System.out.println("목요일");
            break;
        case 5:
            System.out.println("금요일");
            break;
        case 6:
            System.out.println("토요일");
            break;
        default:
            System.out.println("Error");
            break;
    }
    ```

### rule switch문

- `Java 12`부터는 `switch` 표현식에 `case` 블록의 간결한 형태인 `->` 문법을 사용할 수 있다.
- `break` 문이 필요하지 않으며, `yield`를 사용해 값을 반환할 수 있다.

  ```java
  int day = 3;

  String result = switch (day) {
      case 0 -> "일요일";
      case 1 -> "월요일";
      case 2 -> "화요일";
      case 3 -> "수요일";
      case 4 -> "목요일";
      case 5 -> "금요일";
      case 6 -> "토요일";
      default -> "Error";
  };

  System.out.println(result); // "수요일" 출력
  ```
