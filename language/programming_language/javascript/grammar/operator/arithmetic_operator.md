# 산술 연산자(arithmetic operator)

## 산술 이항 연산자(arithmetic binary operation)

- 더하기 연산자(addition operator) : `+`

  > - `x + y`의 꼴에서 `x`와 `y`를 더한 값을 반환한다.
  > - 단, 피연산자 중 하나 이상이 문자열일 경우 문자열 합치기를 수행한다.

- 빼기 연산자(subtraction operator) : `-`

  > - `x - y`의 꼴에서 `x`에서 `y`를 뺀 값을 반환한다.

- 곱하기 연산자(multiplication operator) : `*`

  > - `x * y`의 꼴에서 `x`와 `y`의 곱을 반환한다.

- 나누기 연산자(division operator) : `/`

  > - `x / y`의 꼴에서 `x`를 `y`로 나눈 몫을 반환한다.

- 나머지 연산자(remainder operator) : `%`

  > - `x % y`의 꼴에서 `x`를 `y`로 나눈 나머지를 반환한다.

- 거듭제곱 연산자(exponentiation operator) : `**`

  > - `x ** y`의 꼴에서 `x`의 `y`제곱(x<sup>y</sup>)을 반환한다.

## 산술 단항 연산자(arithmetic unary operator)

- 단항 플러스 연산자(unary plus operator) : `+`

  > - `+x`의 꼴에서 변수 `x`의 부호를 강조한다.
  > - `x`의 타입이 `number`가 아닐 때 `number`로의 형변환을 시도한다.
  >   - `x`를 `number`로 형변환하는 것이 불가능 하면 `NaN`을 반환한다.

- 단항 마이너스 연산자(unary negation operator) : `-`

  > - `-x`의 꼴에서 `x`의 부호를 반전한다.

- 증가 연산자(increment operator) : `++`

  > - 전위 증가(prefix increment operator)
  >   - `++x`의 꼴에서 구문 실행 전 `x`에 `1`을 더한다.
  > - 후위 증가(postfix increment operator)
  >   - `x++`의 꼴에서 구문 실행 후 `x`에 `1`을 더한다.

- 감소 연산자(decrement operator) : `--`

  > - 전위 감소(prefix decrement operator)
  >   - `--x`의 꼴에서 구문 실행 전 `x`에서 `1`을 뺀다.
  > - 후위 감소(postfix decrement operator)
  >   - `x--`의 꼴에서 구문 실행 후 `x`에서 `1`을 뺀다.
