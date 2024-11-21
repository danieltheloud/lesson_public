# Thread 클래스 상속

- `Thread` 클래스를 상속받아 `run` 메소드를 오버라이드하여 스레드의 작업 내용을 정의한다.

  ```java
  class MyThread extends Thread {
      @Override
      public void run() {
          for (int i = 0; i < 5; i++) {
              System.out.println(Thread.currentThread().getName() + " is running
                - " + i);
          }
      }
  }
  ```

- `Thread` 인스턴스의 `start` 메소드를 호출함으로써, `run` 메소드에 정의한 코드를 비동기적으로 실행할 수 있다.

  ```java
  public class Main {
      public static void main(String[] args) {
          MyThread thread1 = new MyThread();
          MyThread thread2 = new MyThread();
          thread1.start();
          thread2.start();
      }
  }
  ```

## Thread 인스턴스 메소드

<!-- TODO -->

## 스레드 상태

> 스레드는 다음 상태를 가질 수 있다.

- `NEW`
  - Thread 객체가 생성되었으나 아직 시작하지 않은 상태.
- `RUNNABLE`
  - 실행 준비가 되었으며, 스케줄러에 의해 실행될 수 있는 상태.
- `BLOCKED`
  - 다른 스레드가 락을 점유하고 있어 대기하는 상태.
- `WAITING`
  - 다른 스레드의 신호를 기다리는 상태.
- `TIMED_WAITING`
  - 지정된 시간 동안 대기.
- `TERMINATED`
  - 실행이 완료된 상태.
