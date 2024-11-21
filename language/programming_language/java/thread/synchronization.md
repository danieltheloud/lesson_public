# 스레드 동기화

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
