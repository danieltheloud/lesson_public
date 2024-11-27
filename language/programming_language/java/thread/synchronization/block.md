# 블록 동기화

- 메서드 전체가 아닌 특정 블록만 동기화가 필요할 때 사용한다.
- `synchronized` 블록을 사용해 특정 객체(object)를 락으로 설정한다.
  - 인스턴스 락
    - `synchronized (i) {}`의 꼴에서 `this` 또는 특정 인스턴스 `i`를 락으로 사용한다.
  - 클래스 락
    - `synchronized (T.class) {}`의 꼴에서 클래스 `T`를 락으로 사용한다.

  ```java
  class MyClass {
      public static void myStaticFunc() {
          synchronized (MyClass.class) {
              // 클래스 객체에 대하여 락이 걸린 코드
          }
      }

      public void myInstanceFunc() {
          synchronized (this) {
              // 인스턴스 객체에 대하여 락이 걸린 코드
          }
      }
  }
  ```
