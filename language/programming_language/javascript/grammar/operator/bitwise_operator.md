# 비트 연산자(bitwise operator)

> 비트 연산을 이해하려면, [`이산 수학`](../../../../../cs/discrete_mathematics.md)의 개념이 필요하다.

## 비트 이항 연산자(bitwise binary operator)

- 비트 AND 연산자(bitwise AND operator) : `&`
  - `x & y` 꼴에서 `x`와 `y`의 이진수 각 자리의 논리 값을 AND 연산한 결과를 반환한다.
- 비트 OR 연산자(bitwise OR operator) : `|`
  - `x | y` 꼴에서 `x` 혹은 `y`의 이진수 각 자리의 논리 값을 OR 연산한 결과를 반환한다.
- 비트 XOR 연산자(bitwise XOR operator) : `^`
  - `x ^ y` 꼴에서 `x` 혹은 `y`의 이진수 각 자리의 논리 값이 **불일치**하는지의 여부를 연산한 결과를 반환한다.

## 비트 단항 연산자(bitwise unary operator)

- 비트 NOT 연산자(bitwise NOT operator) : `~`
  - `~x` 꼴에서 `x`의 이진수 각 자리의 논리 값을 반전(부정)하여 반환한다.
