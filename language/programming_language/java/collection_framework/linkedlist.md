# LinkedList

- `LinkedList`는 `java.util` 패키지에 포함된 컬렉션 클래스이며, `이중 연결 리스트` 클래스이다.
- `LinkedList`는 `List` 인터페이스와 `Deque` 인터페이스를 모두 구현하며, 순서가 있는 데이터 저장 및 큐(queue)와 스택(stack) 구조를 지원한다.
- 요소가 삽입되거나 제거될 때, 연결된 노드의 참조만 변경된다.
- 중간에 요소를 추가하거나 삭제하는 작업이 빠르다.
- 그러나 인덱스를 통한 요소 접근은 `ArrayList`보다 느리다.
- 객체(Object)만 저장할 수 있으며, 원시 자료형은 래퍼 클래스를 사용해서 저장된다.

  ```java
  // 기본적인 LinkedList 선언
  LinkedList<String> list = new LinkedList<>();

  // 요소 추가
  list.add("Dog");
  list.add("Cat");
  list.add("Horse");

  // 요소 출력
  System.out.println(list);   // [Dog, Cat, Horse]

  // 특정 인덱스에 요소 삽입
  list.add(1, "Rabbit");
  System.out.println(list);   // [Dog, Rabbit, Cat, Horse]

  // 첫 번째와 마지막 요소 추가
  list.addFirst("Tiger");
  list.addLast("Elephant");
  System.out.println(list);   // [Tiger, Dog, Rabbit, Cat, Horse, Elephant]

  // 요소 제거
  list.remove("Cat");         // 객체를 사용해서 제거
  list.remove(2);             // 인덱스를 사용해서 제거
  list.removeFirst();         // 첫 번째 요소 제거
  list.removeLast();          // 마지막 요소 제거
  System.out.println(list);   // [Dog, Horse]

  // 요소 접근
  String animal = list.get(1);
  System.out.println(animal); // Horse

  // 크기 확인
  int size = list.size();
  System.out.println(size);   // 2
  ```

- `add`
  - `x.add(e)`의 꼴에서 요소 `e`를 리스트의 끝에 추가한다.
  - `x.add(i, e)`의 꼴에서 인덱스 `i`에 요소 `e`를 삽입한다.
- `addFirst`
  - `x.addFirst(e)`의 꼴에서 요소 `e`를 첫번째 요소로써 삽입한다.
- `addLast`
  - `x.addLast(e)`의 꼴에서 요소 `e`를 리스트의 끝에 추가한다.
  - `x.add(e)`와 같다.
- `remove`
  - `x.remove(i)`의 꼴에서 인덱스 `i`의 요소를 제거한다.
  - `x.remove(o)`의 꼴에서 객체 `o`를 제거한다.
- `removeFirst`
  - `x.removeFirst()`의 꼴에서 첫 번째 요소 제거한다.
- `removeLast`
  - `x.removeLast()`의 꼴에서 마지막 요소 제거한다.
- `get`
  - `x.get(i)`의 꼴에서 인덱스 `i`의 요소를 반환한다.
- `getFirst`
  - `x.getFirst()`의 꼴에서 `e`의 첫번째 요소를 반환한다.
- `getLast`
  - `x.getLast()`의 꼴에서 `e`의 마지막 요소를 반환한다.
- `set`
  - `x.set(i, e)`의 꼴에서 인덱스 `i`의 요소를 새로운 값 e로 변경한다.
- `size`
  - `x.size()`의 꼴에서 리스트의 요소 개수를 반환한다.
- `contains`
  - `x.contains(o)`의 꼴에서 특정 요소 `o`가 리스트에 있는지 여부를 반환한다.
- `isEmpty`
  - `x.isEmpty()`의 꼴에서 리스트가 비어 있는지 여부를 반환한다.
- `clear`
  - `x.clear()`의 꼴에서 리스트의 모든 요소를 제거한다.
