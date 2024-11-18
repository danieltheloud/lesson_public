# 모듈

- 모듈(module)은 파이썬 코드의 재사용을 가능하게 하고, 코드를 구조화하여 가독성과 유지보수성을 높여주는 파일이다.
- 명명법: `스네이크 케이스`

## 모듈 생성

- 파이썬 모듈은 `.py` 확장자를 가진 파일로, 다양한 변수, 함수, 클래스 등을 정의할 수 있다.
- 모듈을 생성하여 필요한 부분에서 `import`하여 사용할 수 있다.
- 새로운 파이썬 파일을 작성하고, 필요한 함수와 클래스 등을 정의한다.

  ```py
  # my_module.py
  def greet(name):
      return f"Hello, {name}!"

  class MyClass:
      def __init__(self, x, y):
         self.x = x
         self.y = y

    def sayTwoNumbers(self):
        print(f"x is {self.x}, y is {self.y}")
  ```

## 모듈 임포트 및 사용

- 다른 파이썬 파일에서 `import` 문을 통해 생성한 모듈을 불러와서 사용할 수 있다.
- 모듈을 불러올 때, **확장자 `.py`는 생략함**에 유의한다.

### 다양한 모듈 임포트

- 기본적으로 모듈 임포트.
  - `import x`의 꼴에서 `x`는 모듈의 이름이다.

  ```py
  # main.py
  import my_module

  # 함수 호출
  print(my_module.greet("John"))  # Hello, John!

  # 클래스 사용
  myInst = my_module.MyClass(10, 20)
  myInst.sayTwoNumbers()  # x is 10, y is 20
  ```

- 네임스페이스를 생략하고, 모듈의 특정 요소을 임포트.
  - `from x import ...y`의 꼴에서 `x`는 모듈의 이름이고 `y`는 추가할 요소이다.
  - `y`가 여러개일 경우, 쉼표로 구분하여 나열한다.
  - `y`의 값으로 와일드 카드 문자 `*`를 사용하면, 모든 요소를 추가한다.

  ```py
  # main.py
  from my_module import *

  # 함수 호출
  print(greet("John"))    # Hello, John!

  # 클래스 사용
  myInst = MyClass(10, 20)
  myInst.sayTwoNumbers()  # x is 10, y is 20
  ```

- 모듈에 별명을 지어서 임포트.
  - `import x as y`의 꼴에서 `x`는 모듈의 이름이고 `y`는 별명이다.

  ```py
  # main.py
  import my_module as mm

  # 함수 호출
  print(mm.greet("John"))  # Hello, John!

  # 클래스 사용
  myInst = mm.MyClass(10, 20)
  myInst.sayTwoNumbers()  # x is 10, y is 20
  ```

### 모듈 경로

- 파이썬은 기본적으로 `sys.path`에 정의된 경로에서 모듈을 탐색한다.
- 모듈이 다른 경로에 있다면, `sys.path`에 해당 경로를 추가할 수 있다.

  ```py
  import sys
  print(type(sys.path))   # <class "list">
  sys.path.append("/path/to/module_directory")
  ```

- 터미널에서 `PYTHONPATH` 환경변수에 모듈의 경로를 지정하면, 해당 경로에서 `python`을 실행한 것으로 취급된다.

  ```bat
  rem command prompt의 경우, set 명령어를 사용하여 환경변수를 등록한다.
  set PYTHONPATH=path\to\my_module && python
  ```

  ```sh
  # shell의 경우, export 명령어를 사용하여 환경변수를 등록한다.
  export PYTHONPATH=path\to\my_module; python3
  ```

## 주의 사항

- 모듈을 임포트할 때, 해당 모듈 내에 모든 코드가 실행된다.
  - 변수의 선언이나, 함수와 클래스의 정의 뿐만 아니라, 변수에 값을 할당하거나 함수의 호출 등도 함께 실행된다.
- 모듈이 임포트되었을 때 특정 코드가 실행되지 않게 하려면, `__name__` 변수를 사용하여 조건문을 작성할 수 있다.
  - `__name__` 변수는 `Python`이 내부적으로 사용하는 변수이다.
    - `__name__` 변수는 직접 실행되었을 때는 "\_\_main\_\_", 임포트 되었을 때는 해당 모듈의 이름을 문자열로 갖는다.

  ```py
  # my_module.py
  if __name__ == "__main__":
      # 모듈이 직접 실행될 때만 실행되는 코드
      print("my_module is being run directly")
  ```

  ```py
  import sys

  print(__name__)       # __main__
  print(sys.__name__)   # sys
  ```
