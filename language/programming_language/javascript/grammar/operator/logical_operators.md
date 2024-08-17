# 논리 연산자(logical operators)

- 논리 AND 연산자(logical AND operator) : `&&`
  - `x && y` 꼴에서 `x`와 `y` 모두 참(`true`)일 경우에만 참을 반환한다.
  - 하나 이상이 거짓(`false`)일 경우, 거짓를 반환한다.
- 논리 OR 연산자(logical OR operator) : `||`
  - `x || y` 꼴에서 `x` 혹은 `y` 중 하나 이상이 참일 경우, 참을 반환한다.
  - 모두 거짓일 경우에만 거짓을 반환한다.
- 널리쉬 병합 연산자(Nullish Coalescing Operator, `??`)
  - `x ?? y` 꼴에서 `x`의 값이 `nullish` 일 때, `y`값을 대신 사용한다.
  - 그렇지 않다면 `x` 값을 그대로 사용한다.

## 논리 단항 연산자(logical unary operator)

- 논리 NOT 연산자(logical NOT operator) : `!`
  - `!x` 꼴에서 `x`의 논리 값을 반전(부정)하여 반환한다.
