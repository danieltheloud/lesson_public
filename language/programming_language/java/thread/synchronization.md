# 동기화 기법

- [메서드 동기화](./synchronization/method.md)
- [블록 동기화](./synchronization/block.md)
- [필드 동기화](./synchronization/field.md)
- [명시적 동기화](./synchronization/explicit.md)

## 동기화 Collections

- `Collections.synchronizedList`, `Collections.synchronizedMap` 등으로 동기화된 컬렉션을 생성한다.
- 내부적으로 메서드에 `synchronized` 키워드를 적용한다.

### Collections 스태틱 메서드

- `Collections.synchronizedList()`: 동기화된 List 반환.
- `Collections.synchronizedMap()`: 동기화된 Map 반환.

<!-- TODO -->

  ```java
  import java.util.*;

  public class Main {
      public static void main(String[] args) {
          List<Integer> synchronizedList = Collections.synchronizedList(new ArrayList<>());

          synchronizedList.add(1);
          synchronizedList.add(2);

          synchronized (synchronizedList) { // 반복은 명시적 동기화 필요
              for (int value : synchronizedList) {
                  System.out.println(value);
              }
          }
      }
  }
  ```

## Semaphore 및 기타 동기화 도구

- `Semaphore`: 리소스 접근 허용 횟수를 제한한다.
- `CountDownLatch`: 특정 조건(카운트가 0)이 충족될 때까지 스레드가 대기하도록 한다.
- `CyclicBarrier`: 여러 스레드가 특정 지점까지 도달할 때까지 대기한 후 작업을 진행한다.

<!-- TODO -->
