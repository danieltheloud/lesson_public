# HashSet

- `HashSet`은 `java.util` 패키지에 포함된 컬렉션 클래스이며, 집합(Set) 컬렉션으로써 요소의 중복을 허용하지 않는다.
- `HashSet`은 내부적으로 해시 테이블(hash table)을 사용해서 요소를 저장하므로, **데이터의 순서를 보장하지 않음**에 유의한다.
- `HashSet`은 빠른 삽입, 삭제, 탐색이 필요한 경우에 적합하다.
- `HashSet`은 `null` 값을 하나만 허용한다.

  ```java
  // 기본적인 HashSet 선언
  HashSet<String> set = new HashSet<>();

  // 요소 추가
  set.add("Apple");
  set.add("Banana");
  set.add("Cherry");

  // 중복된 요소 추가 시 무시
  set.add("Apple");
  System.out.println(set);    // [Apple, Banana, Cherry]

  // 요소 제거
  set.remove("Banana");
  System.out.println(set);    // [Apple, Cherry]

  // 요소 존재 여부 확인
  boolean containsApple = set.contains("Apple");
  System.out.println(containsApple);  // true

  // 크기 확인
  int size = set.size();
  System.out.println(size);   // 2

  // 모든 요소 제거
  set.clear();
  System.out.println(set.isEmpty());  // true
  ```

## HashSet 인스턴스 메소드

- `add`
  - `x.add(e)`의 꼴에서 요소 `e`를 집합에 추가. 이미 존재하는 경우 무시된다.
- `remove`
  - `x.remove(o)`의 꼴에서 객체 `o`를 집합에서 제거.
- `contains`
  - `x.contains(o)`의 꼴에서 특정 요소 `o`가 집합에 있는지 여부를 반환.
- `size`
  - `x.size()`의 꼴에서 집합의 요소 개수를 반환.
- `isEmpty`
  - `x.isEmpty()`의 꼴에서 집합이 비어 있는지 여부를 반환.
- `clear`
  - `x.clear()`의 꼴에서 집합의 모든 요소를 제거.
