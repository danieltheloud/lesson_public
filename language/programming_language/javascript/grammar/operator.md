# 연산자(operator)

- 표현식용(for expression)
  - [산술 연산자(arithmetic operator)](./operator/arithmetic_operator.md)
  - [비교 연산자(comparison operator)](./operator/comparison_operator.md)
  - [논리 연산자(logical operator)](./operator/logical_operators.md)
  - [비트 연산자(bitwise operator)](./operator/bitwise_operator.md)
  - [삼항 연산자(ternary operator)](./operator/ternary_operator.md)
- 명령문용(for statement)
  - [대입 연산자(assignment operator)](./operator/assignment_operator.md)
  - [복합 대입 연산자(compound assignment operator)](./operator/compound_assignment_operator.md)
- 기타 연산자

## 우선순위

- 연산자 사이에는 연산되는 우선순위가 있다.
- 아래는 숫자가 작을 수록 우선순위가 높다는 의미이다(1번이 가장 높은 우선순위).

1. 멤버 접근(`.`, `[]`)
2. 객체화, 함수 호출, 우선 연산자(`new`, `()`, `()`)
3. 증감, 부호, 부정, 타입(`++`, `--`, `+`, `-`, `!`, `typeof`)
4. 거듭제곱(`**`)
5. 곱하기, 나누기, 나머지(`*`, `/`, `%`)
6. 더하기, 빼기(`+`, `-`)
7. 초과, 미만, 이상, 이하(`>`, `<`, `>=`, `<=`)
8. 상등, 부등, 일치, 불일치(`==`, `!=`, `===`, `!==`)
9. 논리 AND(`&&`)
10. 논리 OR(`||`)
11. 널리쉬 병합 연산자, 삼항(`??`, `? :`)
12. 할당, 복합 대입(`=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&&=`, `||=`, `??=` 등)
13. 쉼표 연산자(`,`)

<!-- TODO 정리 필요 -->
