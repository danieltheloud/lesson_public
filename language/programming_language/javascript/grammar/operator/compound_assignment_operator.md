# 복합 대입 연산자(compound assignment operator)

복합 대입 연산자는 특정 연산과 할당을 동시에 수행한다.

## 산술 대입 연산자(arithmetic assignment operator)

- 더하기 대입 연산자(addition assignment operator) : `+=`
  - `x += y`의 꼴에서 `x`와 `y`를 더한 값을 `x`에 재할당한다.
  - `x = x + y`와 같다.
- 빼기 대입 연산자(subtraction assignment operator) : `-=`
  - `x -= y`의 꼴에서 `x`에서 `y`를 뺀 값을 `x`에 재할당한다.
  - `x = x - y`와 같다.
- 곱하기 대입 연산자(multiplication assignment operator) : `*=`
  - `x *= y`의 꼴에서 `x`와 `y`를 곱한 값을 `x`에 재할당한다.
  - `x = x * y`와 같다.
- 나누기 대입 연산자(division assignment operator) : `/=`
  - `x /= y`의 꼴에서 `x`를 `y`로 나눈 값을 `x`에 재할당한다.
  - `x = x / y`와 같다.
- 나머지 대입 연산자(remainder assignment operator) : `%=`
  - `x %= y`의 꼴에서 `x`를 `y`로 나눈 나머지를 `x`에 재할당한다.
  - `x = x % y`와 같다.
- 거듭 제곱 대입 연산자(exponentiation assignment operator) : `**=`
  - `x **= y`의 꼴에서 `x`의 `y`제곱 값을 `x`에 재할당한다.
  - `x = x ** y`와 같다.

## 논리 대입 연산자(logical assignment operators)

- 논리 AND 대입 연산자(logical AND assignment operator) : `&&=`
  - `x &&= y`의 꼴에서 `x`와 `y`가 모두 참인가에 대한 여부를 `x`에 재할당한다.
  - `x = x && y`와 같다.
- 논리 OR 대입 연산자(logical OR assignment operator)  : `||=`
  - `x ||= y`의 꼴에서 `x`와 `y` 중 하나가 참인가 대한 여부를 `x`에 재할당한다.
  - `x = x || y`와 같다.
- 널리쉬 병합 대입 연산자(nullish coalescing assignment operator) : `??=`
  - `x ??= y`의 꼴에서 `x`가 널리쉬일 경우 `y` 값을, 아니라면 `x`값을 재할당한다.
  - `x = x ?? y`와 같다.

## 비트 대입 연산자(bitwise assignment operators)

- 비트 AND 대입 연산자(bitwise AND assignment operator) : `&=`
  - `x &= y`의 꼴에서 `x`와 `y`를 비트 AND 연산한 결과를 `x`에 재할당한다.
  - `x = x & y`와 같다.
- 비트 OR 대입 연산자(bitwise OR assignment operator) : `|=`
  - `x |= y`의 꼴에서 `x`와 `y`를 비트 OR 연산한 결과를 `x`에 재할당한다.
  - `x = x | y`와 같다.
- 비트 XOR 대입 연산자(bitwise XOR assignment operator) : `^=`
  - `x ^= y`의 꼴에서 `x`와 `y`를 비트 XOR 연산한 결과를 `x`에 재할당한다.
  - `x = x ^ y`와 같다.

## 시프트 대입 연산자(shift assignment operator)

- 왼쪽 시프트 대입 연산자(left shift assignment operator) : `<<=`
  - `x <<= y`의 꼴에서 `x`의 이진수를 `y`만큼 왼쪽 시프트 연산한 값을 `x`에 재할당한다.
- 오른쪽 시프트 대입 연산자(right shift assignment operator) : `>>=`
  - `x >>= y`의 꼴에서 `x`의 이진수를 `y`만큼 오른쪽 시프트 연산한 값을 `x`에 재할당한다.
- 부호 없는 오른쪽 시프트 대입 연산자(unsigned right shift assignment operator) : `>>>=`
  - `x >>= y`의 꼴에서 `x`의 이진수를 `y`만큼 부호 없는 오른쪽 시프트 연산한 값을 `x`에 재할당한다.
