# 명시적 동기화

## ReentrantLock

- `ReentrantLock` 클래스는 유연한 동기화 메소드를 제공한다.
- 명시적으로 락을 획득하고 해제할 수 있다.

### ReentrantLock 인스턴스 메소드

- `lock`
  - `x.lock()`의 꼴에서 `ReentrantLock` 인스턴스 `x`가 락을 획득한다.
  - 다른 스레드가 락을 점유 중이면 대기한다.
- `unlock`
  - `x.unlock()`의 꼴에서 `ReentrantLock` 인스턴스 `x`가 락을 해제한다.
- `tryLock`
  - `x.tryLock()`의 꼴에서 `ReentrantLock` 인스턴스 `x`가 락을 시도하고 성공 여부를 반환한다.
- `lockInterruptibly`
  - `x.lockInterruptibly()`의 꼴에서 `ReentrantLock` 인스턴스 `x`가 락 대기 중 인터럽트를 처리할 수 있다.

  ```java
  import java.util.concurrent.locks.ReentrantLock;

  class SharedResource {
      private final ReentrantLock lock = new ReentrantLock();

      public void criticalSection() {
          lock.lock(); // 락 획득
          try {
              System.out.println(Thread.currentThread().getName() + " is in critical section...");
          } finally {
              lock.unlock(); // 락 해제
          }
      }
  }
  ```

## ReentrantReadWriteLock

- `ReentrantReadWriteLock` 클래스는 읽기(read)와 쓰기(write) 작업을 구분하여 동시에 실행 가능한 스레드를 제어한다.
- `ReentrantReadWriteLock` 클래스는 읽기와 쓰기 작업을 위한 각각의 락을 제공한다.
  - 읽기 락: 여러 스레드가 동시에 읽기 가능.
  - 쓰기 락: 단일 스레드만 쓰기 가능.

### ReentrantReadWriteLock 인스턴스 메서드

- `readLock`
  - `x.readLock()`: 읽기 락을 획득.
- `writeLock`
  - `x.writeLock()`: 쓰기 락을 획득.

<!-- TODO -->

  ```java
  import java.util.concurrent.locks.ReentrantReadWriteLock;

  class SharedResource {
      private final ReentrantReadWriteLock lock = new ReentrantReadWriteLock();
      private int data;

      public void writeData(int value) {
          lock.writeLock().lock();
          try {
              data = value;
              System.out.println("Data written: " + value);
          } finally {
              lock.writeLock().unlock();
          }
      }

      public void readData() {
          lock.readLock().lock();
          try {
              System.out.println("Data read: " + data);
          } finally {
              lock.readLock().unlock();
          }
      }
  }
  ```
