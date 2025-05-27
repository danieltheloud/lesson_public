# 자료형(type)

`JavaScript`에는 8가지의 원시 자료형이 있다.

- 원시 자료형(primitive type)
  - `null`

    > - `null` 값을 나타내는 특별한 예약어다.
    > - `JavaScript`는 대소문자를 구분하므로, `null`은 Null, NULL 혹은 다른 변형과도 다르다.

  - `undefined`

    > - 값이 정의되어 있지 않은 최상위 속성이다.

  - `boolean`

    > - 참(`true`)과 거짓(`false`)으로 표현되는 논리값이다.

  - `number`

    > - 정수형(integer) 또는 실수형(float) 숫자이다.

  - `bigint`

    > - 임의 정밀도(arbitrary-precision)의 정수이다.
    > - 숫자 리터럴(literal) 뒤에 `n`을 붙여서 표현한다.

  - `string`

    > - 문자열이다.

  - `symbol` (ECMAScript 2015에 도입)

    > - 인스턴스가 고유하고 불변인 데이터 형이다.

- 객체
  - `object`

## 자료형 변환(data type conversion)

- `JavaScript`는 동적 프로그래밍 언어로써, 변수의 자료형을 자유롭게 바꿀 수 있다.

  ```js
  let thisVar = 1;
  // thisVar 변수는 number 자료형이다.
  console.log(`thisVar 변수는 ${typeof thisVar} 자료형이다`);

  thisVar = 'one';
  // thisVar 변수는 string 자료형이다.
  console.log(`thisVar 변수는 ${typeof thisVar} 자료형이다`);
  ```

### 숫자(number) 자료형과 문자(string) 자료형 간의 변환

- 숫자 자료형을 문자 자료형으로 변환하려면 `toString` 함수를 사용한다.
- `toString`는 `Number`함수의 소유이다.

  ```js
  let num = 10;
  // num의 값은 10이고, 자료형은 number이다.
  console.log(`num의 값은 ${num}이고, 자료형은 ${typeof num}이다.`);

  num = num.toString();
  // num의 값은 10이고, 자료형은 string이다
  console.log(`num의 값은 ${num}이고, 자료형은 ${typeof num}이다.`);
  ```

- 문자 자료형을 숫자 자료형으로 변환하려면 `parseInt` 또는 `parseFloat` 함수를 사용한다.
- `parseInt`와 `parseFloat`은 `window` 객체의 소유이다.

  ```js
  let num1 = '1';
  // num1의 값은 1이고, 자료형은 string이다.
  console.log(`num1의 값은 ${num1}이고, 자료형은 ${typeof num1}이다.`);

  let num2 = '3.14';
  // num2의 값은 3.14이고, 자료형은 string이다.
  console.log(`num2의 값은 ${num2}이고, 자료형은 ${typeof num2}이다.`);

  num1 = parseInt(num1);
  // num1의 값은 1이고, 자료형은 number이다.
  console.log(`num1의 값은 ${num1}이고, 자료형은 ${typeof num1}이다.`);

  num2 = parseFloat(num2);
  // num2의 값은 3.14이고, 자료형은 number이다.
  console.log(`num2의 값은 ${num2}이고, 자료형은 ${typeof num2}이다.`);
  ```

- 정수 꼴로 볼 수 없는 값을 `parseInt`하거나, 실수 꼴로 볼 수 없는 값을 `parseFloat`하는 등의 시도는 오류를 야기한다.
