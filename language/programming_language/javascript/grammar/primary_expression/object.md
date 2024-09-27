# 객체(object)

## this

> - JavaScript에 `this` 키워드는 타 언어들의 `this`와는 차이가 있다.
> - JavaScript의 `this`는 상황에 따라 달라진다.

- 전역 범위에서의 `this`
  - 전역 범위에서의 `this`는 JavaScript의 최상위 객체인 `window`를 가르킨다.

    ```js
    function myFunc() {
        return this;
    }

    console.log(myFunc());  // Window { ... }
    ```

- `object` 범위에서 일반 함수에 의한 `this`
  - `object` 내에서 일반 함수가 `this`를 호출하면, 자신을 **호출**한 상위 객체를 가르킨다.
  - 닷(`.`) 멤버 접근 연사자를 통해서, 해당 `object`의 속성에 접근할 수 있다.

    ```js
    let myObject = {
        word: 'hi',
        getThis: function () {
            return this;
        },
        getWord: function () {
            return this.word;
        }
    };

    console.log(myObject.getThis());    // {word: 'hi', getThis: ƒ, getWord: ƒ}
    console.log(myObject.getWord());    // hi
    ```

- `object` 범위에서 화살표 함수에 의한 `this`
  - `object` 내에서 일반 함수가 `this`를 호출하면, 자신을 **정의**한 상위 객체를 가르킨다.
  - 일반 함수와 달리, 화살표 함수의 `this`는 정의된 위치를 기준으로 동작함에 유의한다.

    ```js
    function myObject() {
        this.myNum = 10;
        return {
            myNum: 20,
            myAnonymousFunc: function () {
                return this.myNum;
            },
            myArrowFunc: () => this.myNum
        };
    }

    let myInstance = new myObject();

    console.log(myInstance.myNum);              // 20
    console.log(myInstance.myAnonymousFunc());  // 20
    console.log(myInstance.myArrowFunc());      // 10
    ```

<!-- TODO -->
