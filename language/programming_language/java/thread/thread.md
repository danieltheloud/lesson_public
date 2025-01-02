# Thread 클래스 상속

- `Thread` 클래스를 상속받아 `run` 메소드를 오버라이드해서 스레드의 수행할 작업을 정의할 수 있다.

  ```java
  class MyThread extends Thread {
      @Override
      public void run() {
          for (int i = 0; i < 5; i++) {
              System.out.println(Thread.currentThread().getName() + " is running - " + i);
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

- `start`
  - `x.start()`의 꼴에서 스레드 `x`를 시작하며, `run` 메소드의 내용을 실행한다.
  - 한 번 실행된 `Thread` 객체를 다시 실행하면 `IllegalThreadStateException` 예외가 발생한다.
- `run`
  - `x.run()`의 꼴에서 스레드 `x`가 실행할 코드가 정의되어 있다.
  - 직접 호출하면 스레드 동작이 아닌 일반 메소드 호출처럼 작동한다.
- `join`
  - `x.join()`의 꼴에서 스레드 `x`가 종료될 때까지 대기한다.
  - `x.join(m)`의 꼴에서 스레드 `x`가 종료될 때까지 대기하되, 최대 밀리초 `m`동안 대기한다.
- `interrupt`
  - `x.interrupt()`의 꼴에서 스레드 `x`를 강제로 종료시킨다.
- `isAlive`
  - `x.isAlive()`의 꼴에서 스레드 `x`가 실행 중인지 여부를 반환한다.
- `sleep`
  - `x.sleep(m)`의 꼴에서 실행 중인 스레드 `x`를 밀리초 `m` 동안 정지한다.
- `getName` / `setName`
  - `x.getName()`의 꼴에서 스레드 `x`의 이름을 반환한다.
  - `x.setName(n)`의 꼴에서 스레드 `x`의 이름을 문자열 `n`으로 설정한다.
- `getPriority` / `setPriority`
  - `x.getPriority()`의 꼴에서 스레드 `x`의 우선순위를 반환한다.
    - 스레드 우선순위를 정수 `1`부터 `10`까지이며, 기본값은 `5`이다.
  - `x.setPriority(p)`의 꼴에서 스레드 `x`의 우선순위를 정수 `p`로 설정한다.
    - 우선순위의 값이 높을 수록 우선순위가 높다.
- `getState`
  - `x.getState()`의 꼴에서 스레드 `x`의 상태를 반환한다.

## 스레드 상태

- `NEW`
  - `Thread` 객체가 생성되었으나 아직 `start` 메소드가 호출되지 않은 상태.
- `RUNNABLE`
  - 스레드가 실행 준비가 된 상태로, 실행 가능하며 스케줄러에 의해 선택될 수 있음.
- `BLOCKED`
  - 스레드가 특정 락을 획득하기 위해 대기 중인 상태.
- `WAITING`
  - 특정 조건 또는 다른 스레드의 신호를 기다리는 상태.
- `TIMED_WAITING`
  - 지정된 시간 동안 대기하는 상태.
- `TERMINATED`
  - 스레드의 실행이 완료된 상태.

## 스레드 동기화

- 스레드는 서로 간섭할 수 있으므로, 공유 자원을 보호하기 위해 동기화가 필요하다.
- `synchronized` 키워드를 사용하면 스레드 간의 충돌을 방지할 수 있다.

  ```java
  class Counter {
      private int count = 0;

      // synchronized 키워드를 사용한 메소드는 동시에 여러 스레드가 접근할 수 없다.
      public synchronized void increment() {
          count++;
      }

      public int getCount() {
          return count;
      }
  }
  ```

  ```java
  public class Main {
      public static void main(String[] args) throws InterruptedException {
          Counter counter = new Counter();

          Thread thread1 = new Thread(() -> {
              for (int i = 0; i < 1000; i++) counter.increment();
          });

          Thread thread2 = new Thread(() -> {
              for (int i = 0; i < 1000; i++) counter.increment();
          });

          thread1.start();
          thread2.start();

          thread1.join();
          thread2.join();

          System.out.println("Final count: " + counter.getCount());
      }
  }
  ```
