# 메서드

- 메서드는 클래스가 소유한 함수(function)이다.
- 메서드에는 `생성자 메서드`(constructor method), `인스턴스 메서드`(instance method), `클래스 메서드`(class method), `스태틱 메서드`(static method)가 있다.
  - `생성자 메서드`는 `인스턴스 객체`를 생성하는 과정에서 자동으로 호출되는 메서드이다.
  - `인스턴스 메서드`는 각각의 `인스턴스 객체`의 속성과 관련된 메서드이다.
  - `클래스 메서드`는 `클래스 객체`의 속성과 관련된 메서드이다.
  - `스태틱 메서드`는 인스턴스나 클래스의 속성과 무관한 메서드이다.
- 메서드의 명명법으로는 `카멜 케이스`를 사용한다.

## 생성자 메서드

- `def __init__(self, ...x):`의 꼴에서 `x`는 `생성자 메서드`를 호출할 때 사용될 `매개 변수`(parameter)이다.
- 생성자 메서드의 첫번째 인자는 `self`여야 한다.

```py
class MyClass:
    def __init__(self, param):
        self.attr = param
```

## 인스턴스 메서드

- `def 변수명(self, ...x)`의 꼴에서 매개 변수 `x`는 인스턴스 메서드가 호출될 때 사용될 `매개 변수`이다.
- 인스턴스 메서드의 첫번째 인자는 `self`여야 한다.

```py
class MyClass:
    def instMethod(self, param):
        pass
```

## 클래스 메서드

- `@classmethod` 데코레이터를 사용하여서 클래스 메서드임을 표현한다.
- `def 변수명(cls, ...x)`의 꼴에서 매개 변수 `x`는 클래스 메서드가 호출될 때 사용될 `매개 변수`이다.
- 클래스 메서드의 첫번째 인자는 `cls`여야 한다.

```py
class MyClass:
    @classmethod
    def clsMethod(cls, param):
        pass
```

## 스태틱 메서드

- `@staticmethod` 데코레이터를 사용하여서 스태틱 메서드임을 표현한다.
- `def 변수명(...x)`의 꼴에서 매개 변수 `x`는 스태틱 메서드가 호출될 때 사용될 `매개 변수`이다.
- 클래스 및 인스턴스의 속성에 영향을 끼치지 않는 메서드를 정의할 때 사용된다.

```py
class MyClass:
    @staticmethod
    def staticMethod(param):
        pass
```
