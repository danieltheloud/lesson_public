# 클래스 인스턴스 생성

- 클래스는 인스턴스를 생성함으로써 실제 객체로 사용할 수 있습니다.
- 클래스를 인스턴스화하면 `__init__` 메소드가 호출되어 인스턴스를 초기화합니다.

  ```py
  class MyClass:
      def __init__(self, x, y):
          self.x = x
          self.y = y
      def sum(self):
          return self.x + self.y
  ```

  ```py
  myInstance = MyClass(10, 20)
  print(myInstance.sum()) # 30
  ```
