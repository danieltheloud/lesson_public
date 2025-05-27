# 논리 연산자(logical operators)

## 논리 이항 연산자(logical binary operator)

- 논리 AND 연산자(logical AND operator) : `&&`

  > - `x && y`의 꼴에서 `x`와 `y` 모두 참(`true`)일 경우에만 참을 반환한다.
  > - 하나 이상이 거짓(`false`)일 경우, 거짓를 반환한다.

- 논리 OR 연산자(logical OR operator) : `||`

  > - `x || y`의 꼴에서 `x` 혹은 `y` 중 하나 이상이 참일 경우, 참을 반환한다.
  > - 모두 거짓일 경우에만 거짓을 반환한다.

## 논리 단항 연산자(logical unary operator)

- 논리 NOT 연산자(logical NOT operator) : `!`

  > - `!x`의 꼴에서 `x`의 논리 값을 반전(부정)해서 반환한다.

## 관계 연산자(relational operator)

- in 연산자(in operator) : `in`

  > - `x in y`의 꼴에서 인덱스(index) 또는 키(key) `x`가 객체 `y`에 포함되어 있는지 여부를 반환한다.

- instanceof 연산자(instanceof operator) : `instanceof`

  > - `x instanceof y`의 꼴에서 객체 `x`가 객체 자료형 `y`의 객체인지 여부를 반환한다.
