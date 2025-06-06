# 비트 연산자(bitwise operator)

> 비트 연산을 이해하려면, [`이산 수학`](../../../../../cs/discrete_mathematics.md)의 개념이 필요하다.

## 비트 이항 연산자(bitwise binary operator)

- 비트 AND 연산자(bitwise AND operator) : `&`

  > - `x & y`의 꼴에서 `x`와 `y`의 이진수 각 자리의 논리 값을 AND 연산한 결과를 반환한다.

- 비트 OR 연산자(bitwise OR operator) : `|`

  > - `x | y`의 꼴에서 `x` 혹은 `y`의 이진수 각 자리의 논리 값을 OR 연산한 결과를 반환한다.

- 비트 XOR 연산자(bitwise XOR operator) : `^`

  > - `x ^ y`의 꼴에서 `x` 혹은 `y`의 이진수 각 자리의 논리 값이 **불일치**하는지의 여부를 연산한 결과를 반환한다.

## 비트 단항 연산자(bitwise unary operator)


- 비트 NOT 연산자(bitwise NOT operator) : `~`

  > - `~x`의 꼴에서 `x`의 이진수 각 자리의 논리 값을 반전(부정)해서 반환한다.

## 비트 시프트 연산자(bitwise shift operator)

- 비트 좌측 시프트 연산자(bitwise left shift operator) : `<<`

  > - `x << n`의 꼴에서 `x`의 이진수를 왼쪽으로 `n` 비트만큼 이동시킨다.
  >   - 이때, 비어 있는 오른쪽 비트들은 `0`으로 채워진다.
  >   - 좌측으로 밀려나는 비트들은 버려진다.
  > - 보통 정수에 2의 `n`승을 곱하는 효과를 얻을 때 사용된다.

- 비트 우측 시프트 연산자(bitwise right shift operator) : `>>`

  > - `x >> n`의 꼴에서 `x`의 이진수를 오른쪽으로 `n` 비트만큼 이동시킨다.
  >   - 부호 있는 정수의 경우, 부호 비트(최상위 비트)를 유지하면서 이동시킨다 (산술 우측 시프트).
  >   - 부호 없는 정수의 경우, 비어 있는 왼쪽 비트들은 `0`으로 채워진다 (논리 우측 시프트).
  > - 보통 정수를 2의 `n`승으로 나누는 효과를 얻을 때 사용된다.

- 비트 부호 없는 우측 시프트 연산자(bitwise unsigned right shift operator) : `>>>` (자바스크립트, 자바 등 일부 언어에서 지원)

  > - `x >>> n`의 꼴에서 `x`의 이진수를 오른쪽으로 `n` 비트만큼 이동시킨다.
  >   - `x`의 부호 여부와 상관없이, 비어 있는 왼쪽 비트들을 항상 `0`으로 채운다.
  > - 이 연산자는 숫자의 부호와 관계없이 비트를 이동시킬 때 유용하다.
