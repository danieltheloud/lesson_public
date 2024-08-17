# 배열(array)

- 가변(resizable) 길이를 가진다.
- 여러 자료형(type)을 혼합하여 담을 수 있다.
- 요소(element)에 대한 접근은, 대괄호(bracket)에 감싼 인덱스(index)로만 가능하다.
  - 요소는 `0`를 포함한 자연수만 가능하다.

## 배열의 선언

- 배열을 선언하려면 대괄호로 감싼다.
  ```js
  // 빈 배열을 선언하려면 대괄호만 나열한다.
  let emptyArray = [];
  // 대괄호 사이에 요소를 나열하여 초기화할 수 있다.
  let mixedArray = [1, 3.14, 'hello'];
  ```

## 요소 읽기(read)

- 배열의 `변수명`과 접근하고자 하는 요소의 인덱스를 대괄호로 감싸서 나열한다.
- 인덱스를 홑따옴표(`'`) 또는 쌍따옴표(`"`)로 감싸도 동일하게 접근이 가능하다.
  ```js
  let myArray = ['one', 'two', 'three'];
  console.log(myArray[0]);    // one이 출력된다.
  console.log(myArray['1']);  // two가 출력된다.
  console.log(myArray["2"]);  // three가 출력된다.
  ```

## 요소 쓰기(write)

- 이는 `JavaScript`의 엔진이 인덱스에 위치한 값을 문자열(`string`)로 강제 형변환하여 사용하기 때문이다.
- 정수 이외의 값을 인덱스로 사용하는 것이 가능하지만, 이렇게 생성된 요소들은 반복자(iterator)를 통한 순회(traversal)가 불가능해지므로 사용하지 않기를 권장한다.
  ```js
  let tmpArray = ['A', 'B', 'C'];
  console.log(tmpArray['0'])  // 0이 출력된다.
  console.log(tmpArray['00']) // undefined이 출력된다.
  
  tmpArray['zero'] = 100;     // 문자열을 인덱스로 사용한다.
  tmpArray[undefined] = 200;  // undefined를 인덱스로 사용한다.
  console.log(tmpArray);      // ['A', 'B', 'C', zero: 100, undefined: 200]이 출력된다.
  // 반복문을 통해 tmpArray의 각 요소를 출력한다.
  for (let i of tmpArray) {
      console.log(i);
  } // 인덱스가 정상적인 A, B, C만 출력된다.
  ```

## 배열의 메소드

<!-- TODO -->
