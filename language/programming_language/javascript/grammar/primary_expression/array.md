# 배열(array)

- 가변(resizable) 길이를 가진다.
- 여러 자료형(type)을 혼합해서 담을 수 있다.
- 요소(element)에 대한 접근은, 대괄호(bracket)에 감싼 인덱스(index)로만 가능하다.
  - 요소는 `0`를 포함한 자연수만 가능하다.

## 선언 및 초기화(declaration and initialization)

- 배열을 리터럴(literal)로 선언 및 초기화하려면 대괄호(`[`, `]`)로 감싼다.
- 배열의 각 요소는 쉼표(`,`)로 구분된다. (comma-seperated)
- 리터럴로 생성하더라도, `Array`의 프로토타입을 갖는다.

  ```js
  // 빈 배열을 선언하려면 대괄호만 나열한다.
  let emptyArray = [];
  // 대괄호 사이에 요소를 나열해서 초기화할 수 있다.
  let mixedArray = [1, 3.14, 'hello'];
  ```

- 배열은 `Array` 생성자를 통해 선언 및 초기화할 수 있다.

  ```js
  // Array의 생성자를 이용해 빈 배열을 선언한다.
  let emptyArray = new Array();
  // 생성자에 인자를 넘겨주면 배열의 요소로 포함되어 초기화된다.
  let mixedArray = new Array(1, 3.14, 'hello');
  ```

- 배열 리터럴의 경우, 쉼표를 연속으로 사용하여, 요소의 사이가 비어있는 배열을 만들 수도 있다.

  ```js
  let initialArray = [1, 2, , 4]; // 요소의 사이가 비어있는 배열을 초기화한다.

  console.log(initialArray);      // [1, 2, empty, 4]
  ```

## 요소 읽기(read)

- 배열의 `변수명`과 접근하고자 하는 요소의 인덱스를 대괄호로 감싸서 나열한다.
- 인덱스를 홑따옴표(`'`) 또는 쌍따옴표(`"`)로 감싸도 동일하게 접근이 가능하다.
- 문자열 `length`를 넣어주면, 배열을 길이를 반환한다.

  ```js
  let myArray = ['one', 'two', 'three'];
  console.log(myArray[0]);    // one
  console.log(myArray['1']);  // two
  console.log(myArray["2"]);  // three

  console.log(myArray['length']);  // 3
  ```

## 요소 쓰기(write)

- 이는 `JavaScript`의 엔진이 인덱스에 위치한 값을 문자열(`string`)로 강제 형변환해서 사용하기 때문이다.
- 정수 이외의 값을 인덱스로 사용하는 것이 가능하지만, 이렇게 생성된 요소들은 반복자(iterator)를 통한 순회(traversal)가 불가능해지므로 사용하지 않기를 권장한다.

  ```js
  let tmpArray = ['A', 'B', 'C'];
  console.log(tmpArray['0'])  // 0
  console.log(tmpArray['00']) // undefined

  tmpArray['zero'] = 100;     // 문자열을 인덱스로 사용한다.
  tmpArray[undefined] = 200;  // undefined를 인덱스로 사용한다.
  console.log(tmpArray);      // ['A', 'B', 'C', zero: 100, undefined: 200]

  // 반복문을 통해 tmpArray의 각 요소를 출력한다.
  for (let i of tmpArray) {
      console.log(i);
  } // 인덱스가 정상적인 A, B, C만 출력된다.
  ```

## 배열의 메소드

### 스태틱 메소드(static method)

- `isArray`
  - `isArray(x)`의 꼴에서 `x`가 배열인지 여부를 반환한다.

    ```js
    console.log(Array.isArray(['a', 'b', 'c']));      // true
    console.log(Array.isArray([]));                   // true
    console.log(Array.isArray(new Array(1, 2, 3)));   // true
    console.log(Array.isArray('abc'));                // false
    ```

### 인스턴스 메소드(instance method)

- `at`
  - `at(x)`의 꼴에서 `x`를 인덱스로 하는 요소를 반환한다.
    - 대괄호를 사용하는 방식과는 다르게, 음수(minus)를 통한 접근이 가능하다.
    - 음수의 경우, 마지막 요소로부터 거꾸로 순서가 매겨진다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.at(1));     // b
    console.log(myArray.at(-2));    // d
    ```

- `concat`
  - `concat(x)`의 꼴에서 배열 `x`를 원본 배열의 마지막에 추가해서 반환한다.
    - 원본 배열이 수정되는 것이 아님에 유의한다.

    ```js
    let myArray1 = ['a', 'b', 'c'];
    let myArray2 = ['d', 'e', 'f'];
    let myArray3 = myArray1.concat(myArray2);

    console.log(myArray1);  // ['a', 'b', 'c']
    console.log(myArray2);  // ['d', 'e', 'f']
    console.log(myArray3);  // ['a', 'b', 'c', 'd', 'e', 'f']
    ```

- `every`
  - `every(x)`의 꼴에서 모든 요소가 메소드 `x`의 인자로써 참(true)을 반환하게 하는지 여부를 반환한다.

    ```js
    let myArray = [2, 4, 6, 8, 10];

    let isOdd = function(x) {
        return x % 2 == 0;
    }   // 짝수인지 여부를 반환하는 메소드이다.

    let isSingleNum = function(x) {
        return x < 10 && x >= 0 && x % 1 == 0;
    }   // 한자리의 자연수인지 여부를 반환하는 메소드이다.

    console.log(myArray.every(isOdd));          // true
    console.log(myArray.every(isSingleNum));    // false
    ```

- `filter`
  - `filter(x)`의 꼴에서 메소드 `x`로 하여금 참을 반환하게 하는 모든 요소들을 얕은 복사해서 배열로 반환한다.
    - 원본 배열이 수정되는 것이 아님에 유의한다.

    ```js
    let myArray = [1, 2, 3, 4, 5, 6, 7, 8, 9];

    console.log(myArray.filter(x => x % 2 == 0));   // [2, 4, 6, 8]
    ```

- `find`
  - `find(x)`의 꼴에서 메소드 `x`의 인자로써 참을 반환하게 하는 첫 요소를 반환한다.

    ```js
    let myArray = [1, 2, 'three', 'four'];

    myArray.find(x => typeof x == 'string');  // 'three'
    ```

- `findIndex`
  - `findIndex(x)`의 꼴에서 메소드 `x`의 인자로써 참을 반환하게 하는 첫 요소의 인덱스를 반환한다.

    ```js
    let myArray = [1, 2, 'three', 'four'];

    myArray.findIndex(x => typeof x == 'string');  // 2
    ```

- `findLast`
  - `findLast(x)`의 꼴에서 `x`의 인자로써 참을 반환하게 하는 마지막 요소를 반환한다.
    - `find` 메소드의 역순으로 순회하기 때문이다.
- `findLastIndex`
  - `findLastIndex(x)`의 꼴에서 `x`의 인자로써 참을 반환하게 하는 마지막 요소의 인덱스를 반환한다.
- `flat`
  - `flat()`의 꼴에서 배열인 요소의 깊이를 한 단계 떨어뜨려서 반환한다.
    - 하위 배열의 인덱스에 해당 요소들이 추가된다.
    - 원본 배열이 수정되는 것이 아님에 유의한다.

    ```js
    let myArray = [1, [2, 3], [4, [5, 6]]];

    console.log(myArray.flat());    // [1, 2, 3, 4, [5, 6]]
    ```

  - `flat(x)`의 꼴에서 `x`번 하위 배열을 원본 배열의 요소에 포함시킨다.
    - `x`가 1 이상일 때, 의미가 있다.
    - `x`가 1일 때, `flat()`과 동일하다.
    - `x`가 `Infinity`일 때, 가능한 최대로 반복한다.

    ```js
    let myArray = [1, [2, [3, [4, [5, 6]]]]];

    console.log(myArray.flat(1));           // [1, 2, [3, [4, [5, 6]]]]
    console.log(myArray.flat(2));           // [1, 2, 3, [4, [5, 6]]]
    console.log(myArray.flat(Infinity));    // [1, 2, 3, 4, 5, 6]
    ```

- `forEach`
  - `forEach(x)`의 꼴에서 각 요소를 메소드 `x`의 인자로 넘겨준다.

    ```js
    let myArray = [1, 2, 3];

    myArray.forEach(x => console.log('hi'.repeat(x)));
    /* hi
     * hihi
     * hihihi
     */
    ```

- `includes`
  - `includes(x)`의 꼴에서 원본 배열에 `x`가 포함되어 있는지 여부를 반환한다.

    ```js
    let myArray = [1, 3, 5];

    console.log(myArray.includes(1));   // true
    console.log(myArray.includes(2));   // false
    ```

- `join`
  - `join()`의 꼴에서 각 요소의 사이를 `,`로 연결해서 문자열을 반환한다.

    ```js
    let myArray = [1, 3.14, 'hi'];

    console.log(myArray.join());    // 1,3.14,hi
    ```

  - `join(x)`의 꼴에서 각 요소의 사이에는 문자열 `x`가 삽입된다.

    ```js
    let myArray = [1, 3.14, 'hi'];

    console.log(myArray.join(''));  // 13.14hi
    console.log(myArray.join('-')); // 1-3.14-hi
    ```

- `map`
  - `map(x)`의 꼴에서 각 요소를 메소드 `x`의 인자로써 넘겨준 결과들을 배열로 반환한다.

    ```js
    let myArray = [1, 2, 3];

    console.log(myArray.map(x => `this is ${x}`));
    // ['this is 1', 'this is 2', 'this is 3']
    ```

- `pop`
  - `pop()`의 꼴에서 마지막 요소를 반환하며, 해당 요소를 제거한다.
    - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = ['one', 'two', 'three'];

    console.log(myArray.pop()); // three
    console.log(myArray);       // ['one', 'two']
    ```

- `push`
  - `push(x)`의 꼴에서 `x`를 원본 배열의 마지막에 추가한다.
  - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = ['one', 'two', 'three'];

    myArray.push('four');
    console.log(myArray);   // ['one', 'two', 'three', 'four']
    ```

- `reduce`
  - `reduce(x)`의 꼴에서 2개의 인자를 받는 메소드 `x`를 반복적으로 호출한 결과를 반환한다.
    - 최초에 0번과 1번 인덱스부터 `x`의 인자로 넘겨준다.
    - 그 후로 이전 연산의 결과값과 다음 인덱스를 반복적으로 넘겨준다.
    - 요소가 하나 뿐이면, 그대로 반환한다.

    ```js
    function myFunc(x, y) {
        let myConcat = `${x} ${y}`;
        console.log(`-> ${myConcat}`);  // 반환할 값을 출력한다.
        return myConcat;
    }

    let myArray1 = [1, 2, 3, 4, 5];
    let myArray2 = [1];

    console.log(myArray1.reduce(myFunc));
    /* -> 1 2
     * -> 1 2 3
     * -> 1 2 3 4
     * -> 1 2 3 4 5
     * 1 2 3 4 5
     */
    console.log(myArray2.reduce(myFunc));
    // 1
    ```

  - `reduce(x, y)`의 꼴에서 `y`는 초기값이다.
    - 최초에 초기값 `y`와 0번 인텍스부터 `x`의 인자로 넘겨준다.

    ```js
    function myFunc(x, y) {
        let myConcat = `${x} ${y}`;
        console.log(`-> ${myConcat}`);  // 반환할 값을 출력한다.
        return myConcat;
    }

    let myArray = ['one', 'two', 'three', `four`, 'five'];

    console.log(myArray.reduce(myFunc, 'zero'));
    /* -> zero one
     * -> zero one two
     * -> zero one two three
     * -> zero one two three four
     * -> zero one two three four five
     * zero one two three four five
     */
    ```

- `reverse`
  - `reverse()`의 꼴에서 요소의 순서를 반전해서 반환한다.
    - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.reverse()); // ['e', 'd', 'c', 'b', 'a']
    console.log(myArray);           // ['e', 'd', 'c', 'b', 'a']
    ```

- `shift`
  - `shift()`의 꼴에서 첫번째 요소를 반환하고, 해당 요소를 제거한다.
    - 나머지 모든 요소의 인덱스를 1씩 감소시킨다.
    - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = ['1st', '2nd', '3rd'];

    console.log(myArray.shift());   // 1st
    console.log(myArray);           // ['2nd', '3rd']
    ```

- `slice`
  - `slice(x)`의 꼴에서 인덱스 `x`부터 마지막 요소까지를 배열로 반환한다.
    - `x`는 음수(minus)일 경우, 마지막 요소로부터 역순으로 순서를 매긴다.
    - 원본 배열을 수정하는 것이 아님에 유의한다.

    ```js
    let myArray = [1, 2, 3, 4, 5];

    console.log(myArray.slice(2));  // [3, 4, 5]
    console.log(myArray.slice(-3)); // [3, 4, 5]
    console.log(myArray);           // [1, 2, 3, 4, 5]
    ```

  - `slice(x, y)`의 꼴에서 인덱스 `y` 이전까지의 배열을 반환한다.
    - `y`는 음수(minus)일 경우, 마지막 요소로부터 역순으로 순서를 매긴다.

    ```js
    let myArray = [1, 2, 3, 4, 5];

    console.log(myArray.slice(1, 4));   // [2, 3, 4]
    console.log(myArray.slice(-4, -1)); // [2, 3, 4]
    console.log(myArray);               // [1, 2, 3, 4, 5]
    ```

- `some`
  - `some(x)`의 꼴에서 하나 이상의 요소가 메소드 `x`의 인자로써 참을 반환하게 하는지 여부를 반환한다.

    ```js
    let myArray = [1, 2];

    console.log(myArray.some(x => x % 2 == 0)); // true
    ```

- `sort`
  - `sort()`의 꼴에서 모든 요소를 `UTF-16`의 기준에서 오름차순으로 정렬해서 반환한다.
    - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = [`alpha`, `beta`, `gamma`, `delta`, 1, 0, 3, 2];

    console.log(myArray.sort());
    // [0, 1, 2, 3, 'alpha', 'beta', 'delta', 'gamma']
    ```

- `splice`
  - `splice(x)`의 꼴에서 인덱스 `x`부터 잘라낸 배열을 반환한다.
    - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.splice(2)); // ['c', 'd', 'e']
    console.log(myArray);           // ['a', 'b']
    ```

  - `splice(x, y)`의 꼴에서 `y`개의 요소를 잘라낸다.
    - `y`가 0이면 잘라내지 않는다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.splice(1, 0));  // []
    console.log(myArray);               // ['a', 'b', 'c', 'd', 'e']
    console.log(myArray.splice(1, 2));  // ['b', 'c']
    console.log(myArray);               // ['a', 'd', 'e']
    ```

  - `splice(x, y, z)`의 꼴에서 잘라낸 위치에 `z`를 삽입한다.
    - `z`는 반환값에 삽입되는 것이 아닌, 원본 배열에 삽입되는 것임에 유의한다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.splice(1, 0, 'f')); // []
    console.log(myArray);                   // ['a', 'f', 'b', 'c', 'd', 'e']
    console.log(myArray.splice(1, 2, 'g')); // ['f', 'b']
    console.log(myArray);                   // ['a', 'g', 'c', 'd', 'e']
    ```

- `toString`
  - `toString()`의 꼴에서 모든 요소들을 문자로써 연결해서 반환한다.
    - 기본적으로 요소들의 사이는 `,`로 연결된다.
    - 배열인 요소가 있다면 그 깊이를 상관없이 해당 배열의 요소를 문자로 취급한다.

    ```js
    let myArray = [1, 'hi', ['one', 'two', [3, 4]]];

    console.log(myArray.toString());    // 1,hi,one,two,3,4
    ```

- `unshift`
  - `unshift(x)`의 꼴에서 `x`를 원본 배열의 앞에 삽입하고, 모든 요소의 수를 반환한다.
    - `x`의 수는 하나 이상일 수 있다.
    - 원본 배열을 수정하는 것임에 유의한다.

    ```js
    let myArray = ['i', 'j', 'k'];

    console.log(myArray.unshift('h'));      // 4
    console.log(myArray);                   // ['h', 'i', 'j', 'k']
    console.log(myArray.unshift('f', 'g')); // 6
    console.log(myArray);                   // ['f', 'g', 'h', 'i', 'j', 'k']
    ```

- `with`
  - `with(x, y)`의 꼴에서 인덱스 `x`의 요소를 `y`로 교체해서 반환한다.
    - 원본 배열을 수정하는 것이 아님에 유의한다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.with(1, 'beta'));   // ['a', 'beta', 'c', 'd', 'e']
    console.log(myArray);                   // ['a', 'b', 'c', 'd', 'e']
    ```

## 인스턴스 속성(instance property)

- `length`
  - `length`는 해당 배열의 요소가 몇개인지의 값을 가진다.

    ```js
    let myArray = ['a', 'b', 'c', 'd', 'e'];

    console.log(myArray.length);    // 5
    ```
