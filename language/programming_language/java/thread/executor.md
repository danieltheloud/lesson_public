# Executor 프레임워크

- `Executor` 프레임워크는 스레드 생성과 관리를 캡슐화하여, 효율적인 병렬 처리를 지원한다.
- 스레드 풀(thread pool)을 사용해 스레드 생성 비용을 줄이고, 스레드 수를 제한하여 시스템 자원을 효과적으로 관리할 수 있다.

## Executors 클래스

- `Executors` 클래스는 다양한 유형의 스레드 풀을 생성하는 정적 메서드를 제공한다.

### Executor 스태틱 메소드

- `newCachedThreadPool`
  - `Executor.newCachedThreadPool()`의 꼴에서 필요에 따라 스레드 수를 동적으로 조정하는 스레드 풀을 생성 및 반환한다.
- `newFixedThreadPool`
  - `Executor.newFixedThreadPool(n)`의 꼴에서 고정 크기 `n`개의 스레드 풀을 생성 및 반환한다.
  - 작업 큐에 대기열을 생성하여 스레드 수를 제한한다.
- `newSingleThreadExecutor`
  - `Executor.newSingleThreadExecutor()`의 꼴에서 단일 스레드로 작업을 처리하는 스레드 풀을 생성 및 반환한다.
- `newScheduledThreadPool`
  - `Executor.newScheduledThreadPool(n)`의 꼴에서 일정 간격으로 작업을 실행하거나 지연 실행을 지원하는 스레드 풀을 생성 및 반환한다.

## Executor / ExecutorService 인터페이스

- `Executor`는 작업 실행을 위한 단순 인터페이스로, 스레드 풀 또는 단일 스레드 작업을 실행한다.
- `ExecutorService`는 `Executor`의 확장 인터페이스로, 스레드 풀의 라이프사이클을 관리하고 추가적인 제어 기능을 제공한다.

### Executor 인스턴스 메소드

- `execute`
  - `x.execute(r)`의 꼴에서 `Runnable` 인스턴스 `r`를 실행한다.

### ExecutorService 인스턴스 메소드

- `submit`
  - `x.submit(c)`의 꼴에서 `Callable` 인스턴스 `c`를 제출하고, 결과를 반환받기 위해 `Future` 객체를 반환한다.
- `shutdown`
  - `x.shutdown()`의 꼴에서 실행 중인 작업이 모두 종료되면 스레드 풀 `x`를 종료한다.
    - 현재 큐에 있는 작업은 실행되지만, 추가 작업은 거부된다.
  - `x.shutdownNow()`의 꼴에서 스레드 풀 `x`의 대기 중인 작업은 취소되고, 실행 중인 작업은 가능한 한 즉시 중단된다.
- `awaitTermination`
  - `x.awaitTermination(t, u)`의 꼴에서 시간 단위 `u`의 `t` 동안 대기한 후, 스레드 풀 `x`가 종료되었는지 여부를 반환한다.

## Executor 프레임워크 사용 예시

- `execute` 메소드 사용

  ```java
  import java.util.concurrent.ExecutorService;
  import java.util.concurrent.Executors;

  public class Main {
      public static void main(String[] args) {
          // 스레드 풀 생성: 최대 2개의 스레드 사용
          ExecutorService executor = Executors.newFixedThreadPool(2);

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

          Runnable task3 = () -> {
              for (int i = 0; i < 5; i++) {
                  System.out.println(Thread.currentThread().getName() + " is running: " + i);
              }
          };

          executor.execute(task1); // 작업 1 추가
          executor.execute(task2); // 작업 2 추가
          executor.execute(task3); // 작업 3 추가 (큐에 대기)

          // 작업이 완료된 후 스레드 풀 종료
          executor.shutdown();

          // shutdown 이후 추가 작업은 IllegalStateException을 유발
          // executor.execute(() -> System.out.println("This will fail"));
      }
  }
  ```

- `submit` 메소드 및 `Future` 인스턴스 사용

  ```java
  import java.util.concurrent.*;

  public class Main {
      public static void main(String[] args) {
          ExecutorService executor = Executors.newFixedThreadPool(2);

          Callable<String> task = () -> {
              Thread.sleep(1000); // 작업 수행
              return "Task completed by " + Thread.currentThread().getName();
          };

          // submit을 통해 작업 제출 및 결과 반환
          Future<String> future = executor.submit(task);

          try {
              System.out.println("Waiting for task to complete...");
              String result = future.get(); // 작업 완료 대기
              System.out.println(result);
          } catch (InterruptedException | ExecutionException e) {
              e.printStackTrace();
          } finally {
              executor.shutdown();
          }
      }
  }
  ```

- `awaitTermination` 메소드 및 `shutdownNow` 메소드 사용

  ```java
  import java.util.concurrent.*;

  public class Main {
      public static void main(String[] args) {
          ExecutorService executor = Executors.newFixedThreadPool(2);

          Runnable longTask = () -> {
              try {
                  Thread.sleep(5000);
                  System.out.println("Task Completed by " + Thread.currentThread().getName());
              } catch (InterruptedException e) {
                  System.out.println("Task Interrupted!");
              }
          };

          executor.execute(longTask);
          executor.execute(longTask);

          executor.shutdown(); // 종료 요청

          try {
              if (!executor.awaitTermination(2, TimeUnit.SECONDS)) {
                  System.out.println("Force shutting down...");
                  executor.shutdownNow(); // 강제 종료
              }
          } catch (InterruptedException e) {
              e.printStackTrace();
          }
      }
  }
  ```
