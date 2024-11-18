# 예외 처리

-  예외(exception)는 프로그램 실행 중에 발생하는 오류를 의미하며, 예외가 발생하면 프로그램의 흐름이 중단될 수 있다.
- 예외 처리는 프로그램의 비정상 종료를 방지하고, 오류 발생 시에 적절한 대처를 통해 프로그램을 안정적으로 유지하는 방법을 제공한다.

## 예외 처리

- `try`문
  - `try` 블럭(block)은 오류가 발생할 가능성이 있는 코드를 포함한다.
- `except`절
  - `except` 블럭은 오류가 발생하면 실행될 코드를 포함한다.
  - `try` 블럭 안에서 오류가 발생하지 않으면 `except` 블럭은 실행되지 않는다.
  - `except`문에서 `Exception` 오류를 명시하면 모든 오류를 포함한다.
  - `except`문은 명시된 오류가 없다면 `Exception`을 명시한 것과 같다.

  ```py
  try:
      # 예외가 발생할 가능성이 있는 코드
      result = 10 / 0
  except Exception:
      # 예외가 발생하면 실행할 코드
      print("오류가 발생했습니다.")
  ```

  ```py
  try:
      # 예외가 발생할 가능성이 있는 코드
      result = 10 / 0
  except:
      # 예외가 발생하면 실행할 코드
      print("오류가 발생했습니다.")
  ```

  - `except`문에서 특정 오류를 명시하면, 해당 오류에 대해서만 작동한다.
  - `except`문은 여러번 사용될 수 있다.

  ```py
  try:
      number = int(input("숫자를 입력하세요: "))
      result = 10 / number
  except ValueError:
      # 숫자가 아닌 값을 입력받았을 때, 실행될 코드
      print("유효한 숫자를 입력해주세요.")
  except ZeroDivisionError:
      # 0을 입력받았을 때, 실행될 코드
      print("0으로 나눌 수 없습니다.")
  ```

  - `as` 키워드와 예외 객체를 활용해 오류에 대한 더 많은 정보를 얻을 수 있다.

  ```py
  try:
      10 / 0
  except ZeroDivisionError as e:
      print(e)    # division by zero
  ```

- `else`절
  - `else` 블럭은 `try` 블럭에서 오류가 발생하지 않았을 경우에 실행된다.
- `finally`절
  - `finally` 블럭은 `try` 블럭의 오류발생 여부와 상관없이 실행된다.
  - `finally` 블럭은 무조건 실행된다.
  - 이전의 블럭이 `return` 키워드를 사용하거나, `exit()` 함수를 호출하는 등, **`try`문을 강제로 종료시키는 코드를 포함하고 있더라도 실행됨**에 유의한다.

  ```py
  try:
      number = int(input("숫자를 입력하세요: "))
      result = 10 // number
  except ValueError:
      # 숫자가 아닌 값을 입력받았을 때, 실행될 코드
      print("유효한 숫자를 입력해주세요.")
  except ZeroDivisionError:
      # 0을 입력받았을 때, 실행될 코드
      print("0으로 나눌 수 없습니다.")
  else:
      # 오류가 발생하지 않았을 경우에 실행될 코드
      print(f"10을 {number}로 나눈 몫은 {int(result)}입니다.")
  finally:
      # 오류발생 여부와 상관없이 실행될 코드
      print("프로그램이 종료됩니다.")
  ```

## 사용자 정의 예외

- 개발자가 새로운 예외 클래스를 정의하여서 필요에 맞게 사용할 수 있다.
- 사용자 정의 예외 클래스는 `Exception` 클래스를 상속받아야 한다.

  ```py
  class CustomError(Exception):
      pass
  ```

  ```py
  try:
      raise CustomError("사용자 정의 예외가 발생하였습니다.")
  except CustomError as e:
      print(e)    # 사용자 정의 예외가 발생하였습니다.
  ```

## 강제 예외 발생

- `raise` 키워드를 사용하면 특정 상황에서 예외를 강제로 발생시킬 수 있다.
- 주로 유효성 검사를 통과하지 못한 경우, 명확하게 예외를 발생시켜 프로그램의 흐름을 제어할 때 사용된다.
  - 예외를 강제로 발생시킬 때는 `raise` 다음에 예외 객체를 지정하고, 추가로 예외 메시지를 포함할 수 있다.

  ```py
  def validate_age(age):
      if age < 0:
          raise ValueError("나이는 0보다 작을 수 없습니다.")
      print(f"입력된 나이는 {age}입니다.")

  try:
      validate_age(-5)
  except ValueError as e:
      print(f"예외 발생: {e}")
  ```

- 사용자 정의 예외 클래스와 함께 `raise`를 사용하면, 보다 세부적인 예외 상황을 정의할 수 있다.

  ```py
  class NegativeNumberError(Exception):
      pass

  def check_positive_number(value):
      if value < 0:
          # 인자가 0보다 작을 경우에 사용자 정의 예외를 발생
          raise NegativeNumberError("양수를 입력해야 합니다.")
      return value

  try:
      check_positive_number(-10)
  except NegativeNumberError as e:
      print(f"사용자 정의 예외 발생: {e}")
  ```
