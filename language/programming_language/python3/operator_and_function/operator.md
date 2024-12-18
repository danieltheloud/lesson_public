# 연산자(operator)

## 단항 연산자(unary operator)

- `+`: 단항 플러스
  - `+x`의 꼴에서 숫자 `x`를 그대로 반환한다.
- `-`: 단항 마이너스
  - `-x`의 꼴에서 숫자 `x`의 부호를 반전해서 출력한다.
- `not`: 부정
  - `not x`의 꼴에서 진릿값 `x`를 반전해서 반환한다.
- `~`: 인버트(invert)
  - `~x`의 꼴에서 정수 `x`의 비트를 반전해서 반환한다.
    - 정수가 아닌 숫자 자료형은 사용할 수 없음에 유의한다.
  - `-(x+1)`와 같다.

## 산술 연산자(arithmetic operator)

- `+`: 더하기
  - `x + y`의 꼴에서 `x`와 `y`를 더한 값을 반환한다.
  - `x`와 `y`가 시퀀스일 경우, 시퀀스 `x`의 뒤에 시퀀스 `y`를 이어붙여 반환한다.
    - 서로 다른 자료형을 혼용할 수 없음에 유의한다.
- `-`: 빼기
  - `x - y`의 꼴에서 `x`에서 `y`를 뺀 값을 반환한다.
  - `x`와 `y`가 집합일 경우 차집합을 반환한다.
- `*`: 곱하기
  - `x * y`의 꼴에서 `x`와 `y`를 곱한 값을 반환한다.
  - `x`와 `y` 중에 하나가 시퀀스이고 나머지 하나가 정수일 경우, 시퀀스를 정수만큼 이어붙여 반환한다.
    - 정수가 `0` 이하일 경우, 빈 시퀀스을 반환한다.
    - 시퀀스끼리 곱할 수는 없음에 유의한다.
- `/`: 나누기
  - `x / y`의 꼴에서 `x`에서 `y`를 나눈 값을 반환한다.
  - 타 언어에서 실수를 나머지 연산한 것과 같음에 유의한다.
- `//`: 몫
  - `x // y`의 꼴에서 `x`에서 `y`를 나눈 몫을 반환한다.
- `%`: 나머지
  - `x % y`의 꼴에서 `x`에서 `y`를 나눈 나머지를 반환한다.
  - `x`가 문자열일 경우, `x`의 포맷(format)에 맞춰서 `y`를 삽입 및 반환한다.
- `**`: 제곱
  - `x ** y`의 꼴에서 `x`를 `y`번 제곱한 값을 반환한다.

## 비교 연산자(comparison operator)

### 값 비교 연산자(value comparison operator)

- `==`: 상등
  - `x == y`의 꼴에서 `x`와 `y`의 값이 같은지 여부를 반환한다.
- `!=`: 부등
  - `x != y`의 꼴에서 `x`와 `y`의 값이 다른지 여부를 반환한다.
- `<`: 미만
  - `x < y`의 꼴에서 `x`의 값이 `y`의 값보다 작은지 여부를 반환한다.
- `>`: 초과
  - `x > y`의 꼴에서 `x`의 값이 `y`의 값보다 큰지 여부를 반환한다.
- `<=`: 이하
  - `x <= y`의 꼴에서 `x`의 값이 `y`의 값보다 작거나 같은지 여부를 반환한다.
- `>=`: 이상
  - `x >= y`의 꼴에서 `x`의 값이 `y`의 값보다 크거나 같은지 여부를 반환한다.

### 신원 비교 연산자(identity comparison operation)

- `is`: 일치
  - `x is y`의 꼴에서 `x`와 `y`의 메모리 위치가 일치하는지 여부를 반환한다.
- `is not`: 불일치
  - `x is not y`의 꼴에서 `x`와 `y`의 메모리 위치가 불일치하는지 여부를 반환한다.

### 소속 확인 연산자(membership test operation)

- `in`: 포함
  - `x in y`의 꼴에서 `x`의 값이 시퀀스 `y`에 포함되는지 여부를 반환한다.
  - 단, `for`문에서는 시퀀스 `y`의 각 요소를 순회하기 위해서 사용됨에 유의한다.
- `not in`: 미포함
  - `x not in y`의 꼴에서 `x`의 값이 시퀀스 `y`에 포함되지 않은지 여부를 반환한다.

## 불리언 연산자(boolean operation)

> 불리언 연산에서 모든 자료형의 숫자 `0`, `False`, 빈 시퀀스, `None`은 `False`로 취급된다.
>
> 그 외의 모든 값은 `True`로 취급된다.

- `and`: 논리곱
  - `x and y`의 꼴에서 진릿값 `x`와 `y` 모두가 `True`일 때, `True`를 반환한다.
  - 그 외에는 `False`를 반환한다.
- `or`: 논리합
  - `x or y`의 꼴에서 진릿값 `x`와 `y` 중에 하나 이상이 `True`일 때, `True`를 반환한다.
  - 그 외에는 `False`를 반환한다.
- `exclusive OR`는 둘중 하나만 `True`일 때, `True`를 반환한다.

## 비트 연산자(bitwise operation)

- `&`: 비트 곱
  - `x & y`의 꼴에서 정수 `x`와 `y`의 각 비트를 `AND` 연산한 결과를 반환한다.
  - `x`와 `y`가 집합일 경우 교집합을 반환한다.
- `|`: 비트 합
  - `x | y`의 꼴에서 정수 `x`와 `y`의 각 비트를 `OR` 연산한 결과를 반환한다.
  - `x`와 `y`가 집합일 경우 합집합을 반환한다.
- `^`: 비트 배타합
  - `x ^ y`의 꼴에서 정수 `x`와 `y`의 각 비트를 `exclusive OR` 연산한 결과를 반환한다.
  - `x`와 `y`가 집합일 경우 대칭차집합을 반환한다.

### 비트 시프트 연산자

- `<<`: 왼쪽 시프트
  - `x << n`의 꼴에서 정수 `x`를 왼쪽으로 `n`개의 비트만큼 밀어내어 반환한다.
  - 밀어내고 남은 자리는 `0`으로 채운다.
- `>>`: 오른쪽 시프트
  - `x >> n`의 꼴에서 정수 `x`를 오른쪽으로 `n`개의 비트만큼 밀어내어 반환한다.
  - 밀어내고 남은 자리는 밀어내기 이전 최상위 비트와 같은 값으로 채운다.

## 대입 표현식(assignment expression)

- `=`: 대입
  - `x = y`의 꼴에서 변수 `x`에 `y`의 값을 할당한다.

### 복합 대입 표현식(complex assignment expression)

- `+=`: 더하기 복합 대입
  - `x += y`의 꼴에서 `x`와 `y`를 더한 값을 `x`에 대입한다.
  - `x = x + y`와 같다.
- `-=`: 빼기 복합 대입
  - `x -= y`의 꼴에서 `x`에서 `y`를 뺀 값을 `x`에 대입한다.
  - `x = x - y`와 같다.
- `*=`: 곱하기 복합 대입
  - `x *= y`의 꼴에서 `x`와 `y`를 곱한 값을 `x`에 대입한다.
  - `x = x * y`와 같다.
- `/=`: 나누기 복합 대입
  - `x /= y`의 꼴에서 `x`에서 `y`를 나눈 값을 `x`에 대입한다.
  - `x = x / y`와 같다.
- `//=`: 몫 복합 대입
  - `x //= y`의 꼴에서 `x`에서 `y`를 나눈 몫을 `x`에 대입한다.
  - `x = x // y`와 같다.
- `%=`: 나머지 복합 대입
  - `x %= y`의 꼴에서 `x`에서 `y`를 나눈 나머지를 `x`에 대입한다.
  - `x = x % y`와 같다.
- `**=`: 제곱 복합 대입
  - `x **= y`의 꼴에서 `x`를 `y`번 제곱한 값을 `x`에 대입한다.
  - `x = x ** y`와 같다.

## 조건 표현식(conditional expression)

- `if else`
  - `x if c else y`의 꼴에서 조건 `c`가 참이면 `x`, 거짓이면 `y`를 반환한다.
  - 타 언어의 "삼항 연산자"(ternary operator)와 유사하다.

## 람다식(lambda)

- `lambda`를 이용해서 익명 함수를 생성한다.
  - `lambda ...x: y`의 꼴에서 `x`를 인자로 받아 `y`의 값을 반환한다.
  - 여러 줄의 로직이 아닌 단일 표현식으로 구성된 간단한 함수를 정의할 때 사용된다.
