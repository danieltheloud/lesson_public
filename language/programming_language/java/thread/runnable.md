# Runnable 인터페이스 구현

- `Runnable` 인터페이스를 구현해서 작업 내용을 정의한 후, `Thread` 생성자에 인자로써 전달해서 실행한다.
- `Runnable` 인터페이스는 함수형 인터페이스이기 때문에, `Java 8` 이상의 버전에서는 람다 표현식으로 작성할 수 있다.
- 이미 다른 클래스를 상속받고 있는 경우에도 구현 가능하다는 점에서, `Thread` 클래스를 상속받는 것과 차이가 있다.

  ```java
  class MyRunnable implements Runnable {
      @Override
      public void run() {
          for (int i = 0; i < 5; i++) {
              System.out.println(Thread.currentThread().getName() + " is running: " + i);
          }
      }
  }
  ```

- `Thread` 클래스의 생성자에 `Runnable` 인스턴스를 넘겨주면, `start` 메소드가 `Runnable` 인스턴스의 `run` 메소드를 사용한다.

  ```java
  public class Main {
      public static void main(String[] args) {
          Thread thread1 = new Thread(new MyRunnable());
          Thread thread2 = new Thread(new MyRunnable());
          thread1.start();
          thread2.start();
      }
  }
  ```
