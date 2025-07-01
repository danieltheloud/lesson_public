# 클로저(closure)

## 클로저

- 클로저(closure)는 `Python`을 포함한 `함수형 프로그래밍 언어`에서 사용되는 개념이다.
- 클로저는 자신이 정의된 `스코프`(scope)의 `비지역 변수`(non-local variable)를 기억하고, 접근할 수 있는 함수를 말한다.
  - `비지역 변수`는 `내부(하위) 함수`(inner function) 내부에서 정의되지 않았지만, 전역 변수도 아닌 변수를 말한다.
  - 즉, `외부(상위) 함수`(outer function)의 `스코프`에서 정의된 변수를 의미한다.

  ```python
  def outer_function(x):
      # 매개변수 x는 outer_function의 지역 변수이자, inner_function의 비지역 변수이다.
      def inner_function(y):
          return x + y
      return inner_function # 내부 함수를 반환한다.

  # outer_function을 호출하고, 반환된 내부 함수를 closer_add_5에 대입한다.
  closer_add_5 = outer_function(5)
  closer_add_10 = outer_function(10)

  # closer_add_5는 outer_function이 종료되었음에도 'x=5'를 기억한다.
  print(closer_add_5(3))  # 출력: 8 (5 + 3)
  print(closer_add_5(7))  # 출력: 12 (5 + 7)

  # closer_add_10는 outer_function이 종료되었음에도 'x=10'을 기억한다.
  print(closer_add_10(3)) # 출력: 13 (10 + 3)
  ```

- 기본적으로 클로저는 외부 함수의 비지역 변수를 읽기만 할 수 있다.
  - 만약 내부 함수에서 외부 함수의 비지역 변수를 **수정**하고 싶다면 `nonlocal` 키워드를 사용해야 한다.

  ```python
  def counter():
      count = 0 # 비지역 변수

      def increment():
          nonlocal count # count가 비지역 변수임을 선언
          count += 1
          return count
      return increment

  my_counter = counter()
  print(my_counter()) # 출력: 1
  print(my_counter()) # 출력: 2
  print(my_counter()) # 출력: 3

  another_counter = counter() # 새로운 카운터 인스턴스
  print(another_counter()) # 출력: 1
  ```

### 클로저의 세 가지 조건

> 어떤 함수가 클로저가 되려면 다음 세 가지 조건을 만족해야 한다.

1. `중첩 함수`(nested function)의 `내부 함수`이어야 한다.
   - 즉, 함수 안에 또 다른 함수가 정의되어 있어야 한다.
2. `내부 함수`는 `외부 함수`에서 선언된 변수를 참조해야 한다.
   - 이 변수가 바로 `비지역 변수`이다.
3. `외부 함수`는 `내부 함수`를 반환해야 한다.
   - `외부 함수`가 실행을 마친 후에도 `내부 함수`는 `비지역 변수`를 계속 기억하고 있어야 한다.

### 클로저의 유용성

클로저는 다음과 같은 상황에서 유용하게 사용될 수 있다.

- 데이터 은닉(`encapsulation`) 및 정보 보호
  - 특정 데이터를 함수 내부에 가두고, 오직 클로저를 통해서만 접근할 수 있도록 만들어서, 외부에서 직접 접근 및 수정하는 것을 방지할 수 있다.
- 부분 적용(partial application) 및 커링(`currying`)
  - 함수의 인자 중 일부를 미리 채워 넣고, 나중에 나머지 인자를 받아 함수를 실행하는 기법이다.
- 콜백(`callback`) 함수
  - 어떤 이벤트가 발생했을 때, 호출될 함수를 미리 정의하고, 그 함수가 주변 환경의 데이터를 사용하도록 만들 수 있다.
- 데코레이터
  - `Python`의 데코레이터는 클로저 개념을 활용하여 함수의 기능을 확장한다.
