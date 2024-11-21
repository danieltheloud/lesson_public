# 추상 클래스

- 추상(abstract) 클래스는 추상 메소드를 가진 클래스이다.
- `a abstract class N {}`의 꼴에서 `a`는 접근 제한자, `N`은 클래스의 이름이다.
- 추상 클래스는 스스로 인스턴스를 생성할 수 없다.
- 추상 클래스로 인스턴스를 생성하려면, 상속을 받은 클래스에서 모든 추상 메소드를 정의해야만 한다.

  ```java
  public abstract class MyClass {
      // 추상 메소드를 포함한 필드 및 메소드
  }
  ```

## 추상 메소드

- 추상 메소드는 블럭이 없다.
- `a abstract T N(...x);`의 꼴에서 `a`는 접근 제한자, `T`는 반환 타입, `N`은 함수의 이름, `x`는 매개 변수이다.

  ```java
  public abstract class MyClass {
      public abstract void myMethod();
  }
  ```
