# 연산자

- 연산자(operator)는 `변수`, `리터럴 상수`, `심볼릭 상수` 등을 조합해서 표현식을 이루며, 연산한 결과를 반환한다.

## 산술 연산자(arithmetic operator)

- `+`: 더하기
  - `x + y`의 꼴에서 숫자 `x`와 숫자 `y`를 더한 값을 반환한다.
- `-`: 빼기
  - `x - y`의 꼴에서 숫자 `x`에서 숫자 `y`를 뺀 값을 반환한다.
- `*`: 곱하기
  - `x * y`의 꼴에서 숫자 `x`와 숫자 `y`를 곱한 값을 반환한다.
- `/`: 나누기
  - `x / y`의 꼴에서 숫자 `x`를 `0`이 아닌 숫자 `y`로 나눈 값을 반환한다.
  - **`x`와 `y`가 모두 정수라면, 몫을 반환하고, 나머지는 버림**에 유의한다.
- `%`: 나머지
  - `x % y`의 꼴에서 정수 `x`를 `0`이 아닌 정수 `y`로 나눈 나머지를 반환한다.

## 비교 연산자(comparison operator)

- `==`: 상등
  - `x == y`의 꼴에서 `x`와 `y`가 같은지 여부를 반환한다.
- `!=`: 부등
  - `x != y`의 꼴에서 `x`와 `y`가 다른지 여부를 반환한다.
- `<`: 미만
  - `x < y`의 꼴에서 `x`가 `y`보다 작은지 여부를 반환한다.
- `<=`: 이상
  - `x <= y`의 꼴에서 `x`가 `y`보다 작거나 같은지 여부를 반환한다.
- `>`: 초과
  - `x > y`의 꼴에서 `x`가 `y`보다 큰지 여부를 반환한다.
- `>=`: 이상
  - `x >= y`의 꼴에서 `x`가 `y`보다 크거나 같은지 여부를 반환한다.

## 논리 연산자(logical operators)

- `&&`: AND
  - `x && y`의 꼴에서 조건 `x`와 조건 `y`가 모두 참인지 여부를 반환한다.
- `||`: OR
  - `x || y`의 꼴에서 조건 `x`와 조건 `y` 중에서 하나라도 참인지 여부를 반환한다.
- `!`: NOT
  - `!x`의 꼴에서 조건 `x`의 논리값을 반전하여 반환한다.

## 증감 연산자

- `++`: 증가 연산자(increment operator)
  - 전위 증가 연산자
    - `++x`의 꼴에서 변수 `x`의 값을 `1` 증가시킨 후, 증가된 값을 반환한다.
  - 후위 증가 연산자
    - `x++`의 꼴에서 변수 `x`의 값을 반환한 후, `1` 증가시킨다
- `--`: 감소 연산자(decrement operator)
  - 전위 감소 연산자
    - `--x`의 꼴에서 변수 `x`의 값을 `1` 감소시킨 후, 감소된 값을 반환한다.
  - 후위 감소 연산자
    - `x--`의 꼴에서 변수 `x`의 값을 반환한 후, `1` 감소시킨다.

## 비트 연산자(bitwise operator)

- `&`: 비트 AND
  - `x & y`의 꼴에서 숫자 `x`와 숫자 `y`의 비트를 비교하여 둘 다 `1`일 때만 `1`인 값을 반환한다.
- `|`: 비트 OR
  - `x | y`의 꼴에서 숫자 `x`와 숫자 `y`의 비트를 비교하여 하나라도 `1`이면 `1`인 값을 반환한다.
- `^`: 비트 XOR
  - `x ^ y`의 꼴에서 숫자 `x`와 숫자 `y`의 비트를 비교하여 다르면 `1`, 같으면 `0`인 값을 반환한다.
- `~`: 비트 NOT
  - `~x`의 꼴에서 숫자 `x`를 비트 단위로 반전한 값을 반환한다.
- `<<`: 왼쪽 시프트
  - `x << n`의 꼴에서 숫자 `x`의 비트를 `n`만큼 왼쪽으로 이동시키고, 오른쪽 빈자리는 `0`으로 채운다.
- `>>`: 오른쪽 시프트
  - `x >> n`의 꼴에서 숫자 `x`의 비트를 `n`만큼 오른쪽으로 이동시키고, 왼쪽 빈자리는 부호 비트로 채운다.

## 대입 연산자(assignment operator)

- `=`: 대입
  - `x = y`의 꼴에서 변수 `x`에 값 `y`를 대입한다.
  - 대입의 대상이 되는 변수를 `lvalue`, 대입되는 값을 `rvalue`라고 한다.

### 복합 대입 연산자(compound assignment operator)

- `+=`
  - `x += y`의 꼴에서 `x = x + y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `-=`
  - `x -= y`의 꼴에서 `x = x - y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `*=`
  - `x *= y`의 꼴에서 `x = x * y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `/=`
  - `x /= y`의 꼴에서 `x = x / y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `%=`
  - `x %= y`의 꼴에서 `x = x % y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `&=`
  - `x &= y`의 꼴에서 `x = x & y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `|=`
  - `x |= y`의 꼴에서 `x = x | y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `^=`
  - `x ^= y`의 꼴에서 `x = x ^ y`와 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `<<=`
  - `x <<= n`의 꼴에서 `x = x << n`과 같은 동작을 수행하며 결과를 `x`에 대입한다.
- `>>=`
  - `x >>= n`의 꼴에서 `x = x >> n`과 같은 동작을 수행하며 결과를 `x`에 대입한다.
