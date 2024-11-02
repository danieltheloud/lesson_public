# numbers.Number: 숫자

## numbers.Integral: 정수형

### int: 정수

- 기본적으로 `숫자 리터럴`은 10진수로 인식된다.
- `0b`로 시작하면 2진수로 인식된다.
- `0o`로 시작하면 8진수로 인식된다.
- `0x`로 시작하면 16진수로 인식된다.

```py
print(10)       # 10
print(0b1010)   # 10
print(0o12)     # 10
print(0xa)      # 10
```

### bool: 불린(boolean)

- `bool`은 `int`의 자식형(subtype)이다.
- 연산에서 `False`는 `0`, `True`는 `1`로 취급된다.
- 문자열로 반환되는 경우는 `False`, `True`로 반환된다.

```py
myBool1 = False
myBool2 = True

print(10 + myBool1) # 10
print(10 + myBool2) # 11
print(myBool1)      # False
print(myBool2)      # True
```

- 논리식에서 `None`, `0`, 빈 시퀀스, 빈 컬렉션은 `False`로 취급된다.
  - `0`이 아닌 수, 비어있지 않은 시퀀스, 비어있지 않은 컨렉션은 `True`로 취급된다.

## numbers.Real: 실수형

### float: 부동소수점(floating-point)

- 타 언어의 `double`(8byte) 자료형과 같다.
- `Python`에는 타 언어의 `float`(4byte) 자료형이 없다.

```py
myFloat = 1/3

print(myFloat)  # 0.3333333333333333
```

## numbers.Complex: 복소수형

### complex: 복소수

- 허수를 가질 수 있다.
- 허수(`i`)는 j로 표현된다.

## 산술 연산자(arithmetic operator)

- `+`: 더하기
  - `x + y`의 꼴에서 `x`와 `y`를 더한 값을 반환한다.
- `-`: 빼기
  - `x - y`의 꼴에서 `x`에서 `y`를 뺀 값을 반환한다.
- `*`: 곱하기
  - `x * y`의 꼴에서 `x`와 `y`를 곱한 값을 반환한다.
- `/`: 나누기
  - `x / y`의 꼴에서 `x`에서 `y`를 나눈 값을 반환한다.
  - **타 언어에서 실수를 나누기 연산한 것과 같음**에 유의한다.
- `//`: 몫
  - `x // y`의 꼴에서 `x`에서 `y`를 나눈 몫을 반환한다.
- `%`: 나머지
  - `x % y`의 꼴에서 `x`에서 `y`를 나눈 나머지를 반환한다.
- `**`: 제곱
  - `x ** y`의 꼴에서 `x`를 `y`번 제곱한 값을 반환한다.

## 논리 연산자(logical operator)

- `not`: 부정
  - `not x`의 꼴에서 진릿값 `x`를 반전하여 반환한다.
- `and`
  - `x and y`의 꼴에서 `x`와 `y`가 모두 참이면 참을 반환하고, 그 외에는 거짓을 반환한다.
  - `x & y`의 꼴에서 `x`와 `y`가 모두 진릿값이라면 결과가 같다.
- `or`
  - `x or y`의 꼴에서 `x`와 `y`가 모두 참이면 참을 반환하고, 그 외에는 거짓을 반환한다.
  - `x | y`의 꼴에서 `x`와 `y`가 모두 진릿값이라면 결과가 같다.
