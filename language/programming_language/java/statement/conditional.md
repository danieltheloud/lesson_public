# 조건문

조건문은 특정 조건에 따라 코드의 실행 흐름을 제어하는 데에 사용된다.

## if문

> if문은 조건이 참일 때 특정 코드를 실행한다.

- if문은 `if`, `else if`, `else`문으로 구성되며, `if`를 제외한 나머지는 선택사항이다.
  - `if (c) {x}`의 꼴에서 조건식 `c`가 참이면, 스코프 `x`를 실행한다.
  - `else if (c) {x}`의 꼴에서 조건식 `c`가 참이면, 스코프 `x`를 실행한다.
  - `else {x}`의 꼴에서 앞선 모든 조건이 거짓이면, 스코프 `x`를 실행한다.

## switch문

> switch문은 변수 값에 따라 여러 경우(case) 중 하나를 선택하여 실행한다.

- switch문은 표현식의 값과 일치하는 `case`를 찾아 해당 블록을 실행한다.
- `default` 블록을 추가하여 어떠한 `case`와도 일치하지 않을 때의 실행 코드를 정의할 수 있다.
- 각 `case`에는 `break` 문을 사용하여 블록 실행 후 `switch` 문을 빠져나간다.

    ```java
    int day = 3;
    String dayName;

    switch (day) {
        case 1:
            dayName = "월요일";
            break;
        case 2:
            dayName = "화요일";
            break;
        case 3:
            dayName = "수요일";
            break;
        default:
            dayName = "기타";
            break;
    }

    System.out.println(dayName); // "수요일" 출력
    ```

## 삼항 연산자 (?:)

> 삼항 연산자는 조건에 따라 두 값 중 하나를 선택할 때 사용된다. `if`문의 간단한 대체로 유용하다.

- 형태는 `조건 ? 값1 : 값2`이다.
- 조건이 참이면 `값1`을, 거짓이면 `값2`를 반환한다.

    ```java
    int number = 10;
    String result = (number > 0) ? "양수" : "음수 또는 0";
    System.out.println(result); // "양수" 출력
    ```

<!-- TODO -->
