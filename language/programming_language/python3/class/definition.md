# 클래스 정의

- 클래스를 정의할 때는 `class` 키워드와 함께 클래스명 및 콜론(`:`)을 사용한다.
- 클래스의 명명법으로는 파스칼 케이스를 사용한다.

  ```py
  class MyClass:
      pass
  ```

## 속성과 메소드

> 클래스는 속성(attribute)과 메소드(method)를 포함할 수 있다.

- [속성](./definition/attribute.md)
- [메소드](./definition/method.md)

## 키워드

- `self` 키워드는 해당 클래스로 생성될 인스턴스(instance) 객체를 의미한다.
  - 타 언어의 `this` 키워드와 유사하다.
  - `self` 키워드의 뒤에 `맴버 접근 연산자`(member access operator) `.`을 사용하면 해당 인스턴스 객체의 속성을 가르킨다.
- `cls` 키워드는 해당 클래스 객체를 의미한다.
  - `cls` 키워드의 뒤에 `맴버 접근 연산자` `.`을 사용하면 해당 클래스 객체의 속성을 가르킨다.
