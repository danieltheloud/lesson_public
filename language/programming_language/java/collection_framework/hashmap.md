# HashMap

- `HashMap`은 `java.util` 패키지에 포함된 컬렉션 클래스이며, 키-값 쌍(Key-Value Pair)을 저장하는 자료구조이다.
- 해시 테이블 기반으로 구현되며, 키의 중복을 허용하지 않고, 값은 중복될 수 있다.
- `HashMap`은 순서를 보장하지 않으며, 순서가 중요할 경우 `LinkedHashMap`을 사용한다.
- `HashMap`은 `null` 키와 `null` 값을 허용한다. 단, `null` 키는 하나만 허용된다.

  ```java
  // 기본적인 HashMap 선언
  HashMap<String, Integer> map = new HashMap<>();

  // 요소 추가
  map.put("Apple", 3);
  map.put("Banana", 5);
  map.put("Cherry", 2);

  // 요소 출력
  System.out.println(map);    // {Apple=3, Banana=5, Cherry=2}

  // 키를 통한 값 접근
  int value = map.get("Banana");
  System.out.println(value);  // 5

  // 특정 키 존재 여부 확인
  boolean hasKey = map.containsKey("Cherry");
  System.out.println(hasKey); // true

  // 특정 값 존재 여부 확인
  boolean hasValue = map.containsValue(3);
  System.out.println(hasValue);   // true

  // 요소 제거
  map.remove("Apple");
  System.out.println(map);    // {Banana=5, Cherry=2}

  // 크기 확인
  int size = map.size();
  System.out.println(size);   // 2

  // 모든 요소 제거
  map.clear();
  System.out.println(map.isEmpty());  // true
  ```

## HashMap 주요 메소드

- `put`
  - `x.put(k, v)`의 꼴에서 키 `k`와 값 `v`의 쌍을 추가한다.
  - 키 `k`가 이미 존재한다면 값 `v`로 수정한다.
- `get`
  - `x.get(k)`의 꼴에서 키 `k`에 해당하는 값을 반환한다.
  - 해당 키가 없으면 `null` 반환한다.
- `remove`
  - `x.remove(k)`의 꼴에서 키 `k`에 해당하는 요소를 제거한다.
- `containsKey`
  - `x.containsKey(k)`의 꼴에서 키 `k`가 존재하는지 여부를 반환한다.
- `containsValue`
  - `x.containsValue(v)`의 꼴에서 값 `v`가 존재하는지 여부를 반환한다.
- `size`
  - `x.size()`의 꼴에서 맵의 요소 개수를 반환한다.
- `isEmpty`
  - `x.isEmpty()`의 꼴에서 맵이 비어 있는지 여부를 반환한다.
- `clear`
  - `x.clear()`의 꼴에서 모든 요소를 제거한다.
