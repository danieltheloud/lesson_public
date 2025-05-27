# 연산자(operator)

- 표현식용(for expression)
  - [산술 연산자(arithmetic operator)](./operator/arithmetic_operator.md)
  - [비교 연산자(comparison operator)](./operator/comparison_operator.md)
  - [논리 연산자(logical operator)](./operator/logical_operators.md)
  - [비트 연산자(bitwise operator)](./operator/bitwise_operator.md)
  - [삼항 연산자(ternary operator)](./operator/ternary_operator.md)
  - [멤버 접근 연산자(member access operator)](./operator/member_access_operator.md)
  - [널리쉬 병합 연산자(nullish coalescing operator)](./operator/nullish_coalescing_operator.md)
- 명령문용(for statement)
  - [대입 연산자(assignment operator)](./operator/assignment_operator.md)
  - [복합 대입 연산자(compound assignment operator)](./operator/compound_assignment_operator.md)

## 우선순위

- 연산자 사이에는 연산되는 우선순위가 있다.
- 아래는 숫자가 작을 수록 우선순위가 높다는 의미이다(1번이 가장 높은 우선순위).

1. 멤버 접근, 그룹화
   - `obj.prop` : 점 표기법 멤버 접근
   - `obj['prop']` : 괄호 표기법 멤버 접근
   - `func()` : 함수 호출
   - `new Class()` : 객체 생성
   - `(expression)` : 그룹화 / 우선 연산자
2. 단항 연산자 - 증감, 부호, 논리 부정, 타입
   - `++`, `--` : 증가/감소, 후위
   - `!`, `~` : 논리 NOT, 비트 NOT
   - `+`, `-` : 단항 플러스, 단항 마이너스
   - `typeof`, `void`, `delete` : 타입 검사, `undefined` 반환, 프로퍼티 삭제
   - `new` : 인수 없는 객체 생성
3. 거듭제곱
   - `**` : 거듭제곱
4. 곱셈, 나눗셈, 나머지
   - `*` : 곱셈
   - `/` : 나눗셈
   - `%` : 나머지
5. 덧셈, 뺄셈
   - `+` : 덧셈
   - `-` : 뺄셈
6. 비트 시프트
   - `<<` : 좌측 시프트
   - `>>` : 부호 유지 우측 시프트
   - `>>>` : 부호 없는 우측 시프트
7. 관계 (비교) 연산자
   - `>`, `<`, `>=`, `<=` : 보다 큼, 보다 작음, 크거나 같음, 작거나 같음
   - `in`, `instanceof` : 속성 존재 확인, 인스턴스 확인
8. 상등 (Equality) 연산자
   - `==`, `!=` : 동등, 부등
   - `===`, `!==` : 일치, 불일치
9. 비트 AND
   - `&` : 비트 AND
10. 비트 XOR
    - `^` : 비트 XOR
11. 비트 OR
    - `|` : 비트 OR
12. 논리 AND
    - `&&` : 논리 AND
13. 논리 OR
    - `||` : 논리 OR
14. 널리쉬 병합 및 삼항 연산자
    - `??` : 널리쉬 병합
    - `? :` : 삼항 조건
15. 할당 (Assignment) 연산자
    - `=` : 기본 할당
    - `+=`, `-=`, `*=`, `/=`, `%=`, `**=`, `<<=`, `>>=`, `>>>=`, `&=`, `^=`, `|=` : 복합 할당
    - `&&=`, `||=`, `??=` : 논리 할당
16. 쉼표 연산자
    - `,` : 여러 표현식을 한 줄에 작성하고 마지막 표현식의 값을 반환
