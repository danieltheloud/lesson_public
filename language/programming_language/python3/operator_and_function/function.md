# 함수(function)

- 함수에는 내장 함수와 사용자 정의 함수가 있다.

## 사용자 정의 함수(user defined function)

- [함수의 정의(definition)](./function/definition.md)
- [함수의 호출(call)](./function/call.md)

## 내장 함수(built-in function)

- [표준 입출력(standard I/O) 함수](./function/standard_io.md)
- [파일 입출력(file I/O) 함수](./function/file_io.md)

## 람다 함수

- `람다 함수`는 한 줄로 작성할 수 있는 `익명 함수`로, `lambda` 키워드를 사용하여 정의한다.
- `람다 함수`는 `return` 키워드를 사용하지 않아도 표현식의 결괏값을 리턴한다.
- `콜백 함수`로써 간단한 연산이나 짧은 함수를 정의하기 위해서 자주 사용된다.

```py
func = lambda x, y: x + y
variable = func(arg1, arg2)
```
