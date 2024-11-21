# Runnable 인터페이스 구현

- `Runnable` 인터페이스를 구현하여 작업 내용을 정의한 후, `Thread` 객체에 전달해 실행한다.

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

- `Thread` 클래스의 생성자에 `Runnable` 인스턴스를 넘겨주면, `start` 메소드가 `Runnable` 인스턴스에 정의된 `run` 메소드를 사용한다.

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
