# 비교 연산자(comparison operator)

## 일치성 연산자(equality operators)

- 동등 연산자(느슨한 동등 연산자; equality operator) : `==`

  > - `x == y`의 꼴에서 `x`와 `y`의 값이 같은가의 여부를 반환한다.
  > - **타입 비교를 하지 않음에 유의해야 한다.**

- 부등 연산자(느슨한 부등 연산자; inequality operator) : `!=`

  > - `x != y`의 꼴에서 `x`와 `y`의 값이 다른가의 여부를 반환한다.
  > - **타입 비교를 하지 않음에 유의해야 한다.**

- 일치 연산자(엄격한 동등 연산자; strict equality operator) : `===`

  > - `x === y`의 꼴에서 `x`와 `y`의 **값과 타입이 모두 같은가**의 여부를 반환한다.

- 불일치 연산자(엄격한 부등 연산자; strict inequality operator) : `!==`

  > - `x !== y`의 꼴에서 `x`와 `y`의 **값 혹은 타입이 다른가**의 여부를 반환한다.

## 관계성 연산자(relational operators)

- 초과 연산자(greater than operator) : `>`

  > - `x > y`의 꼴에서 `x`가 `y`보다 큰가의 여부를 반환한다.

- 미만 연산자(less than operator) : `<`

  > - `x < y`의 꼴에서 `x`가 `y`보다 작은가의 여부를 반환한다.

- 이상 연산자(greater than or equal operator) : `>=`

  > - `x >= y`의 꼴에서 `x`가 `y`보다 큰거나 같은가의 여부를 반환한다.

- 이하 연산자(less than or equal operator) : `<=`

  > - `x <= y`의 꼴에서 `x`가 `y`보다 작거나 같은가의 여부를 반환한다.

- 인스턴스오브 연산자 : `instanceof`

  > - `x instanceof y`의 꼴에서 `x`가 `y`의 인스턴스(instance)인가의 여부를 반환한다.
  > - `y` 생성자(constructor)의 `prototype`이 `x`에 `prototype chain`되어있는지가 기준이 되다.

- in 연산자 : `in`

  > - `x in y`의 꼴에서 `x`가 `y`객체의 `property` 또는 `prototype chain`에 포함되어 있는가의 여부를 반환한다.
