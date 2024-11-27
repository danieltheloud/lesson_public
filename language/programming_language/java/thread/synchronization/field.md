# 필드 동기화

## volatile 필드

- `volatile` 필드는 메인 메모리 접근을 보장한다.
  - 중앙 처리 장치(`CPU`) 캐시 대신 메인 메모리(`RAM`)에서 직접 읽고 쓰도록 강제된다.
- `volatile` 필드는 가시성(visibility)을 보장한다.
  - 일반 필드는 스레드마다 캐시에서 읽고 쓰기 때문에, 다른 스레드에서 업데이트된 값을 바로 보지 못할 수 있지만, `volatile` 필드는 항상 최신 값을 보장한다.
- `volatile` 필드는 명령 재정렬(instruction reordering)을 방지한다.
  - 컴파일러(compiler)는 `CPU`의 실행 성능을 높이기 위해 코드 실행 순서를 최적화할 수 있으나, `volatile` 필드는 이 최적화를 제한해서 필드 읽기 및 쓰기의 순서가 코드에 작성된 그대로 유지한다.
  - 읽기 및 쓰기 작업만 안전하고, 복합 작업(읽기 후 갱신 등)에서는 동기화 작업이 필요하다.
- `volatile` 필드는 원자성(atomicity)을 보장하지 않는다.
  - `volatile` 필드는 값을 수정하는 복합 연산이 동기화되지 않은 상태로 수행된다.
  - 복합 연산에는 `synchronized` 키워드나 `Atomic` 클래스를 사용하는 것이 적합하다.
- `volatile`은 복잡한 상태 동기화에는 부적합하다.
  - `volatile`은 간단한 플래그, 상태 변수 등에 적합하며, 복잡한 작업(예: 여러 변수 간의 관계를 동기화)은 `synchronized`나 다른 동기화 메커니즘을 사용해야 합니다.

  ```java
  public class Main {
      private static volatile boolean stop = false;

      public static void main(String[] args) {
          // 스레드 1: 반복 작업 수행
          Thread worker = new Thread(() -> {
              while (!stop) {
                  // 작업 수행
              }
              System.out.println("Worker stopped.");
          });

          // 스레드 2: stop 플래그 설정
          Thread stopper = new Thread(() -> {
              try {
                  Thread.sleep(1000); // 1초 대기
              } catch (InterruptedException e) {
                  Thread.currentThread().interrupt();
              }
              stop = true;
              System.out.println("Stop flag set.");
          });

          worker.start();
          stopper.start();
      }
  }
  ```

## Atomic 계열 클래스

- `java.util.concurrent.atomic` 패키지는 원자적(atomic) 연산을 제공하여, 동기화가 필요 없는 고성능의 쓰레드 안전 작업을 지원한다.
- `synchronized` 키워드를 사용한 동기화보다 일반적으로 더 가볍고 효율적이다.
- `non-blocking` 방식 동기화를 사용한다.
- `CAS` 알고리즘을 사용한다.
- `AtomicInteger`, `AtomicIntegerArray`, `AtomicLong`, `AtomicLongArray`, `AtomicBoolean`, `AtomicReference` 등의 클래스를 포함한다.

  ```java
  import java.util.concurrent.atomic.AtomicInteger;

  class SharedResource {
      private AtomicInteger counter = new AtomicInteger();

      public void increment() {
          int value = counter.incrementAndGet(); // 원자적으로 값 증가
          System.out.println("Counter: " + value);
      }
  }
  ```

<!-- TODO -->
