# ArrayList

- `ArrayList`는 `java.util` 패키지에 포함된 컬렉션 클래스이며, 동적 배열 클래스이다.
- `ArrayList`는 제네릭 사용해서 다양한 타입의 객체를 저장할 수 있다.
- 크기가 고정된 배열(array)과 달리, `ArrayList`는 요소가 추가되거나 제거되면 자동으로 크기가 조정되므로, 더 유연하게 사용할 수 있다.
- `ArrayList`는 배열처럼 인덱스를 사용해서 요소에 빠르게 접근할 수 있다.
- `ArrayList`는 객체만 저장할 수 있으며, 원시 자료형은 자동으로 래퍼 클래스로 변환된다.
- `ArrayList`는 중복된 값을 가질 수 있다.

  ```java
  // 기본적인 ArrayList 선언
  ArrayList<String> list = new ArrayList<>();

  // 요소 추가
  list.add("Apple");
  list.add("Banana");
  list.add("Cherry");

  // 요소 출력
  System.out.println(list);   // [Apple, Banana, Cherry]

  // 특정 인덱스에 요소 삽입
  list.add(1, "Blueberry");
  System.out.println(list);   // [Apple, Blueberry, Banana, Cherry]

  // 요소 제거
  list.remove("Banana");      // 객체를 사용해서 제거
  list.remove(0);             // 인덱스를 사용해서 제거
  System.out.println(list);   // [Blueberry, Cherry]

  // 요소 접근
  String fruit = list.get(1);
  System.out.println(fruit);  // Cherry

  // 크기 확인
  int size = list.size();
  System.out.println(size);   // 2
  ```

## ArrayList 인스턴스 메소드

- `add`
  - `x.add(e)`의 꼴에서 요소 `e`를 `x`의 끝에 추가(append)한다.
  - `x.add(i, e)`의 꼴에서 인덱스 `i`에 요소 `e`를 삽입(insert)한다.
- `remove`
  - `x.remove(i)`의 꼴에서 인덱스 `i`의 요소를 제거한다.
  - `x.remove(o)`의 꼴에서 객체 `o`를 제거한다.
- `get`
  - `x.get(i)`의 꼴에서 인덱스 `i`의 요소를 반환한다.
- `set`
  - `x.set(i, e)`의 꼴에서 인덱스 `i`의 요소를 새로운 값 `e`로 변경한다.
- `size`
  - `x.size()`의 꼴에서 `x`의 요소 개수를 반환한다.
- `contains`
  - `x.contains(o)`의 꼴에서 특정 요소 `o`가 `x`에 있는지 여부를 반환한다.
- `isEmpty`
  - `x.isEmpty()`의 꼴에서 `x`가 비어 있는지 여부를 반환한다.
- `clear`
  - `x.clear()`의 꼴에서 `x`의 모든 요소를 제거한다.
