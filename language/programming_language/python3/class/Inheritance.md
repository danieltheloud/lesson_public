# 클래스의 상속

- 상속(inheritance)을 통해서 기존 클래스(`부모 클래스` 또는 `슈퍼 클래스`)의 속성과 메소드를 새로운 클래스(`자식 클래스` 또는 `서브 클래스`)에서 물려주고 확장할 수 있다.
- 상속을 통해 기존 클래스를 확장해서 새로운 기능을 추가할 수 있다.
- 자식 클래스는 부모 클래스의 모든 속성 및 메소드를 자동으로 상속받는다.
- 파이썬에서는 클래스 정의 시 괄호 안에 부모 클래스 이름을 지정해서 상속 관계를 명시한다.

  ```py
  class ParentClass:
      pass

  class ChildClass(ParentClass):
      pass
  ```

## 키워드

- `super` 키워드는 부모 클래스 객체를 의미한다.
- 부모 클래스의 속성 및 메소드에 접근하려면 `super()`로부터 맴버 접근 연산자를 통해서 접근한다.

  ```py
  class ParentClass:
      def __init__(self):
          print("Parent Constructor")

  class ChildClass(ParentClass):
      def __init__(self):
          super().__init__()  # 부모 클래스의 생성자를 호출
          print("Child Constructor")
  ```

## 메소드 오버라이딩(method overriding)

- 상속받은 메소드를 자식 클래스에서 **재정의**하는 것을 메소드 `오버라이딩`이라고 한다.
- `오버라이딩`된 메소드는 자식 클래스의 인스턴스에서 호출될 때, 부모 클래스의 메소드가 아닌 자식 클래스의 메소드가 실행된다.

  ```py
  class ParentClass:
      def func(self):
          print("This is a method from the parent class")

  class ChildClass(ParentClass):
      def func(self):
          print("This is a method from the child class")

  obj = ChildClass()
  obj.func()  # This is a method from the child class
  ```

## 다중 상속(multiple inheritance)

- 다중 상속은 하나의 자식 클래스가 동시에 여러 부모 클래스로부터 상속받는 것을 의미합니다.
- 다중 상속 시, 부모 클래스의 이름을 쉼표로 구분해서 선언합니다.

  ```py
  class FatherClass:
      def show(self):
          print("This is the father class")

  class MotherClass:
      def display(self):
          print("This is the mother class")

  class ChildClass(FatherClass, MotherClass):
      pass

  # Usage
  obj = ChildClass()
  obj.show()    # This is the father class
  obj.display() # This is the mother class
  ```

### 다중 상속의 문제점

- 다이아몬드 문제
  - 부모 클래스들이 같은 조상 클래스를 상속할 때, 상속 관계가 다이아몬드 형태를 이루며, 메소드 탐색 순서(`MRO`; Method Resolution Order)에 의해 어떤 메소드가 호출될지 혼란이 생길 수 있습니다.
- 충돌
  - 서로 다른 부모 클래스에서 같은 이름의 메소드나 속성을 정의할 경우, 자식 클래스에서의 메소드 호출이 예기치 않은 결과를 초래할 수 있습니다.

  ```py
  class A:
         def show(self):
             print("A")

  class B(A):
      def show(self):
          print("B")

  class C(A):
      def show(self):
          print("C")

  class D(B, C):
      pass

  obj = D()
  obj.show()  # B (파이썬의 MRO에 따라 결정됨)
  ```

#### MRO(Method Resolution Order) 확인

- MRO를 확인하려면 `__mro__` 속성이나 `inspect` 모듈의 `getmro()` 함수를 사용할 수 있습니다.

```py
...
print(D.__mro__)    # (<class "__main__.D">, <class "__main__.B">, <class "__main__.C">, <class "__main__.A">, <class "object">)
```

```py
from inspect import *
...
print(getmro(D))    # (<class "__main__.D">, <class "__main__.B">, <class "__main__.C">, <class "__main__.A">, <class "object">)
```
