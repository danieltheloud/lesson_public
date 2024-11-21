# 표준 입출력(standard I/O) 함수

## 출력

- `print`
  - `print(...x)`의 꼴에서 `x`의 값을 터미널에 출력한다.
  - `print` 함수의 `키워드 매개 변수`로써 `sep`, `end` 등이 있다.
  - `sep` 매개 변수는 `매개 변수`들의 사이에 삽입될 문자열이다.
    - 기본 값은 `" "`이다.
  - `end` 매개 변수는 출력물의 마지막에 삽입될 문자열이다.
    - 기본 값은 `"\n"`이다.

  ```py
  print(arg1, arg2, sep=" ", end="\n")
  ```

## 입력

- `input`
  - `input()`의 꼴에서 사용자로부터 문자열을 입력받고, 그대로 반환한다.
  - `input(x)`의 꼴에서 문자열 `x`를 출력함과 동시에, 사용자로부터 문자열을 입력받고, 그대로 반환한다.
  - 입력받은 데이터는 항상 **문자열 자료형으로 반환**되므로, 필요하다면 `형변환`을 사용할 수 있다.

  ```py
  user_input = input("Enter your name: ")
  print("Hello, " + user_input)
  ```

  ```py
  age = int(input("Enter your age: "))
  print("Next year, you will be", age + 1)
  ```
