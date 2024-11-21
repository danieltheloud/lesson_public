# Executor 프레임워크 사용

- `Executor`를 통해 스레드 풀을 관리하며 효율적으로 병렬 처리를 수행할 수 있다.
- 스레드 생성 및 관리의 부담이 줄어들고, 성능이 최적화된다.

  ```java
  import java.util.concurrent.ExecutorService;
  import java.util.concurrent.Executors;

  public class Main {
      public static void main(String[] args) {
          ExecutorService executor = Executors.newFixedThreadPool(2); // 스레드 풀 크기 지정

          Runnable task1 = () -> {
              for (int i = 0; i < 5; i++) {
                  System.out.println(Thread.currentThread().getName() + " is running: " + i);
              }
          };

          Runnable task2 = () -> {
              for (int i = 0; i < 5; i++) {
                  System.out.println(Thread.currentThread().getName() + " is running: " + i);
              }
          };

          executor.execute(task1);
          executor.execute(task2);
          executor.shutdown();  // 작업 완료 후 종료
      }
  }
  ```
