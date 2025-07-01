# 데코레이터(decorator)

- `Python`의 데코레이터는 기존 함수의 코드를 직접 수정하지 않고도, 해당 함수의 기능을 확장하거나 변경할 수 있도록 해주는 고급 문법이다.
- 데코레이터는 클로저 개념을 기반으로 작동한다.
  - 주로 `로깅`, `성능 측정`, `접근 제어`, `트랜잭션 처리` 등과 같은 횡단 관심사(`cross-cutting concerns`)를 분리하여 코드의 재사용성을 높이고 유지보수를 용이하게 만든다.

  ```py
  def my_decorator(func): # 데코레이터 함수는 데코레이트할 함수를 인자로 받는다.
      def wrapper(*args, **kwargs): # wrapper 함수는 원본 함수의 인자를 받다.
          print("함수 실행 전에 뭔가 할 수 있다.") # 함수 실행 전 수행할 작업
          result = func(*args, **kwargs) # 원본 함수 실행
          print("함수 실행 후에 뭔가 할 수 있다.") # 함수 실행 후 수행할 작업
          return result # 원본 함수의 반환값 반환
      return wrapper # wrapper 함수(클로저)를 반환한다.

  @my_decorator # '@' 구문을 사용하여 함수에 데코레이터를 적용한다.
  def say_hello(name):
      print(f"안녕하세요, {name}님!")
      return f"Hello, {name}!"

  # say_hello 함수를 호출하면 my_decorator가 적용된 형태로 실행된다.
  returned_value = say_hello("김철수")
  print(f"반환된 값: {returned_value}")
  ```

  - 위 코드에서 `@my_decorator`는 `say_hello = my_decorator(say_hello)`와 동일한 의미를 가진다.
    - 즉, `my_decorator`가 `say_hello` 함수를 인자로 받아 `wrapper` 함수를 반환하고, 이 `wrapper` 함수가 원래 `say_hello`라는 이름으로 호출되도록 덮어씌우는 것이다.
  - 이때 `wrapper` 함수는 `say_hello` 함수가 정의될 당시의 스코프에 있는 `func` (즉, 원본 `say_hello` 함수)를 기억하고 접근할 수 있는 클로저가 된다.

### 데코레이터의 유용성

- 로깅(logging)
  - 함수의 호출, 인자, 반환 값 등을 기록하여 디버깅이나 운영 모니터링에 활용한다.
- 성능 측정(performance measurement)
  - 함수의 실행 시간을 측정하여 성능 병목 지점을 파악한다.
- 인증 및 권한 부여(authentication & authorization)
  - 특정 함수가 실행되기 전에 사용자 인증 여부나 접근 권한을 확인한다.
- 캐싱(caching)
  - 함수의 결과를 캐시하여 동일한 인자로 호출될 때 다시 계산하지 않고 저장된 결과를 반환하도록 한다.
- 예외 처리(error handling)
  - 특정 함수에서 발생하는 예외를 일관된 방식으로 처리한다.

### 데코레이터 체인

- 하나의 함수에 여러 개의 데코레이터를 적용할 수도 있다.
- 이를 데코레이터 체인(`decorator chain`)이라고 부르며, 데코레이터는 위에서 아래 순서로 적용된다.

  ```py
  def decorator_one(func):
      def wrapper(*args, **kwargs):
          print("--- decorator_one 시작 ---")
          result = func(*args, **kwargs)
          print("--- decorator_one 종료 ---")
          return result
      return wrapper

  def decorator_two(func):
      def wrapper(*args, **kwargs):
          print("--- decorator_two 시작 ---")
          result = func(*args, **kwargs)
          print("--- decorator_two 종료 ---")
          return result
      return wrapper

  @decorator_one
  @decorator_two
  def decorated_function():
      print("원본 함수 실행 중!")

  decorated_function()
  ```

- 클로저와 데코레이터는 파이썬에서 함수형 프로그래밍 패러다임을 이해하고 활용하는 데 매우 중요한 개념이다.
- 특히 데코레이터는 파이썬의 강력하고 파이써닉(pythonic)한 코드 작성에 필수적인 요소이다.
