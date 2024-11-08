# 클래스의 상속

- 상속(inheritance)을 통해서 기존 클래스(`부모 클래스` 또는 `슈퍼 클래스`)의 속성과 메서드를 새로운 클래스(`자식 클래스` 또는 `서브 클래스`)에서 물려주고 확장할 수 있다.
- 상속을 통해 기존 클래스를 확장하여 새로운 기능을 추가할 수 있다.
- 자식 클래스는 부모 클래스의 모든 속성 및 메서드를 자동으로 상속받는다.
- 파이썬에서는 클래스 정의 시 괄호 안에 부모 클래스 이름을 지정하여 상속 관계를 명시한다.

```py
class ParentClass:
    pass

class ChildClass(ParentClass):
    pass
```

## 키워드

- `super` 키워드는 부모 클래스 객체를 의미한다.
- 부모 클래스의 속성 및 메소드에 접근하려면 `super()`로부터 맴버 접근 연산자를 통해서 접근한다.

## 메서드 오버라이딩(method overriding)

- 상속받은 메서드를 자식 클래스에서 **재정의**하는 것을 메서드 `오버라이딩`이라고 한다.
- `오버라이딩`된 메서드는 자식 클래스의 인스턴스에서 호출될 때, 부모 클래스의 메서드가 아닌 자식 클래스의 메서드가 실행된다.

```py
class ParentClass:
    def func():
        # 부모 클래스에서의 정의

class ChildClass(ParentClass):
    def func():
        # 자식 클래스에서의 재정의
```

## 다중 상속(multiple inheritance)

- 다중 상속은 하나의 자녀가 동시에 여러 부모로부터 상속을 받는 것이다.

```py
class FatherClass:
    pass

class MotherClass:
    pass

class ChildClass(FatherClass, MotherClass):
    pass
```

### 다중 상속의 문제점

<!-- TODO -->
