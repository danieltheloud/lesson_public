# API

- `Java`에서 제공하는 API(application programming interface)는 프로그램 개발에 자주 사용되는 내장 클래스(built-in class) 및 인터페이스의 모음, 라이브러리라고도 부른다.

## StringBuilder

- `StringBuilder`는 `Java`에서 문자열을 조작할 때 사용되는 클래스이다.
- 불변(immutable)이라는 특징을 가지는 `String` 클래스와 달리,  `StringBuilder`는 가변(mutable) 객체로 문자열을 변경할 수 있다.
- `StringBuilder`는 새로운 객체를 생성하지 않고 문자열을 조작할 수 있다.
- `String` 객체를 여러 번 연결할 때보다 `StringBuilder`를 사용하면 성능이 더 우수하다.
- `StringBuilder`는 동기화(synchronization)를 제공하지 않기 때문에 단일 스레드 환경에서 사용된다.

## StringBuffer

- `StringBuffer`는 `StringBuilder`와 비슷하지만, 스레드 안전성을 제공한다.
- `StringBuffer`는 메서드가 `synchronized` 키워드로 보호되어 있어 스레드에 안전하다.
- 동기화가 필요하지 않은 경우에는 `StringBuilder`보다 성능이 떨어질 수 있다.

### StringBuilder와 StringBuffer의 인스턴스 메소드

- `append()`
  - `x.append(y)`의 꼴에서 문자열 `x`의 뒤에 문자열 `y`를 추가한다.
- `insert()`
  - `x.insert(y, z)`의 꼴에서 문자열 `x`의 `y`번째 인덱스에 문자열 `z`를 삽입한다.
- `delete()`
  - `x.delete(y, z)`의 꼴에서 문자열 `x`의 인덱스가 `y` 이상, `z` 미만인 문자들을 삭제한다.
- `reverse()`
  - `x.reverse()`의 꼴에서 문자열 `x`의 모든 문자를 역순으로 변환한다.
- `toString()`
  - `x.toString()`의 꼴에서 현재 `StringBuilder` 객체의 문자열 표현을 반환한다.

## Math

- `Math` 클래스는 수학적 계산을 위한 다양한 메서드를 제공한다.
- `Math` 클래스의 메서드는 모두 `static`으로 선언되어 있으며, 객체를 생성하지 않고 바로 사용할 수 있다.

### Math의 스태틱 메소드

- `abs()`
  - `Math.abs(x)`의 꼴에서 `x`의 절대값을 반환한다.
- `sqrt()`
  - `Mate.sqrt(x)`의 꼴에서 `x`의 제곱근을 반환한다.
- `pow()`
  - `Mate.pow(x, y)`의 꼴에서 `x`의 `y` 거듭제곱 값을 반환한다.
- `round()`
  - `Mate.round(x)`의 꼴에서 `x`의 반올림한 값을 반환한다.
- `max()`
  - `Mate.max(x, y)`의 꼴에서 `x`와 `y` 중에서 더 큰 값을 반환한다.
- `min()`
  - `Mate.min(x, y)`의 꼴에서 `x`와 `y` 중에서 더 작은 값을 반환한다.
- `random()`
  - `Mate.random()`의 꼴에서 0.0과 1.0 사이의 임의의 double 값을 반환한다.
