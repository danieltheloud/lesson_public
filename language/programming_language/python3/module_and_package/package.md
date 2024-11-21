# 패키지

- 여러 모듈을 모아놓은 디렉토리(directory)를 패키지(package)라고 하며, 패키지는 모듈을 계층적으로 구성할 수 있게 해준다.
- 패키지의 디렉토리에는 `__init__.py` 파일을 포함시켜야 한다.
- 명명법: `스네이크 케이스`

  ```txt
  my_package/
  ├── __init__.py
  ├── module1.py
  └── module2.py
  ```

> `python 3.3` 버전부터는 `__init__.py` 파일이 없어도 패키지로 인식한다`(PEP 420)`.
>
> 하지만 하위 버전 호환을 위해 `__init__.py` 파일을 생성하는 것이 안전한 방법이다.

## 상대적 임포트

- 패키지 내부에서 모듈 간에 임포트를 하는 경우, `.`과 `..`를 사용해 상대적 임포트를 활용할 수 있다.
  - `.`은 현재 디렉토리, `..`은 부모 디렉토리를 의미한다.

  ```py
  # my_package/module1.py
  from .module2 import farewell  # 현재 패키지에서 module2를 가져옴

  def combined_message():
      return f"{greet()} and {farewell()}"
  ```

### \_\_init\_\_.py

- `__init__.py`는 패키지가 처음 로드될 때 실행되며, 이 파일을 통해 특정 모듈이나 함수만 외부에 노출할 수 있다.
  - `from . import ...x`의 꼴에서 `x`는 현재의 패키지에 포함된 모듈이다.
  - `x`가 여러개일 경우, 쉼표로 구분해서 나열한다.
  - 패키지를 임포트하면 모듈이 함께 임포트되므로, 모듈의 초기화에 사용할 수 있다.
  - 패키지로부터 와일드 카드 문자 `*`로 임포트할 수 없다.

  ```py
  # my_package/__init__.py
  from . import module1
  from . import module2
  ```

  - `__all__ = [..."x"]`의 꼴에서 `x`는 현재의 패키지에 포함된 모듈이다.
  - `x`가 여러개일 경우, 쉼표로 구분해서 나열한다.
  - 패키지를 임포트하더라도 모듈이 함께 임포트되지 않으므로, 모듈의 초기화에 사용할 수 없다.
  - `__all__` 변수에 요소로써 이름이 등록된 모듈은, 패키지로부터 와일드 카드 문자 `*`로 임포트할 수 있다.

  ```py
  # my_package/__init__.py
  __all__ = ["module1", "module2"]
  ```

- 패키지 수준에서 변수와 함수를 정의할 수 있다.

  ```py
  # my_package/__init__.py
  VERSION = 1.0

  def print_version_info():
      print(f"The version is {VERSION}.")
  ```

- 패키지를 불러들이는 초기 과정에서 실행되어야 할 코드를 작성할 수 있다.

  ```py
  # my_package/__init__.py
  print("initialized")
  ```

## 패키지 생성

- 패키지는 디렉토리 내에 모듈 파일들이 포함된 형태로 구성된다.
- 디렉토리에는 `__init__.py` 파일을 추가해서 패키지임을 `Python`에 알려야 한다.

## 패키지 임포트 및 사용

- 패키지를 임포트할 때는 `import`문을 사용하여, 패키지 디렉토리의 위치를 지정하면 된다.
- 패키지를 임포트하더라도, **`__init__.py`에 명시되어 있지 않은 모듈 및 요소에는 접근할 수 없음**에 유의한다.

### 다양한 패키지 임포트

- 기본적인 패키지 임포트.
  - `import x`의 꼴에서 `x`는 패키지의 경로를 포함한 이름이다.
  - 패키지를 통해서 모듈에 접근하려면, **해당 패키지의 `__init__.py` 파일에 우선 임포트해주어야 함**에 유의한다.
  - `__init__.py` 파일에 모듈을 임포트할 때, **와일드 카드 문자 `*`를 사용할 수 없음**에 유의한다.

  ```py
  from . import module1
  ```

  ```py
  # main.py
  import path.to.my_package

  # 함수 호출
  print(path.to.my_package.module1.greet("John")) # Hello, John!

  # 클래스 사용
  myInst = path.to.my_package.module1.MyClass(10, 20)
  myInst.sayTwoNumbers()  # x is 10, y is 20
  ```

- 특정 모듈만 임포트.
  - `from x import ...y`의 꼴에서 `x`는 패키지의 경로를 포함한 이름이고, `y`는 모듈의 이름이다.
  - `y`가 여러개일 경우, 쉼표로 구분해서 나열한다.
  - `y`의 값으로 와일드 카드 문자 `*`를 사용하면, 해당 패키지의 `__init__.py` 파일에서 리스트 자료형 변수 `__all__`의 요소로써 이름이 등록된 모듈들을 사용할 수 있다.
    - **`__all__` 변수에 추가되지 않은 모듈을 사용할 수 없음**에 유의한다.

  ```py
  # my_package.__init__.py
  __all__ = ["module1", "module2"]
  ```

  ```py
  # main.py
  from path.to.my_package import *

  # 함수 호출
  print(module1.greet("John"))    # Hello, John!
  print(module1.farewell("John")) # Good bye, John!

  # 클래스 사용
  myInst = module1.MyClass(10, 20)
  myInst.sayTwoNumbers()  # x is 10, y is 20
  ```

- 패키지에 별명을 지어서 임포트.
  - `import x as y`의 꼴에서 `x`는 패키지의 경로를 포함한 이름이고 `y`는 별명이다.

  ```py
  # main.py
  import path.to.my_package as pack

  # 함수 호출
  print(pack.module1.greet("John"))   # Hello, John!

  # 클래스 사용
  myInst = pack.module1.MyClass(10, 20)
  myInst.sayTwoNumbers()    # x is 10, y is 20
  ```

## 서브 패키지

- 패키지 내에 서브 디렉토리를 추가해 서브 패키지를 구성할 수 있다.
  - 계층 구조를 통해 모듈을 더 조직적으로 관리할 수 있다.

  ```txt
  my_package/
  ├── __init__.py
  ├── module1.py
  ├── module2.py
  └── sub_package/
      ├── __init__.py
      └── submodule1.py
  ```

  ```py
  # my_package/sub_package/submodule1.py
  def sub_greet():
      return "Hello from submodule1"
  ```

  ```py
  # main.py
  from my_package.sub_package import submodule1

  print(submodule1.sub_greet())   # Hello from submodule1
  ```

## 주의 사항

- 패키지의 디렉토리 이름과 모듈 이름은 `Python` 예약어와 겹치지 않도록 한다.
