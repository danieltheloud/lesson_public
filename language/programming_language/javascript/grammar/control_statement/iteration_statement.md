# 반복문(iteration statement)

## 전통적인 for문

- `for`
  - `for (x; y; z) {l}`의 꼴에서 조건 `y`가 참인 동안 `l`을 반복한다.
    ```js
    for (let i = 0; i < 5; i++) {
        console.log(i);
    }
    /* 1
     * 2
     * 3
     * 4
     * 5
     */
    ```

## 향상된 for문

- `for...of`
  - `for (const x of y) {z}`의 꼴에서 `y`의 각 요소인 `x`를 순회하며 `z`를 반복한다.
    ```js
    let myArray = ['a', 'b', 'c'];

    for (const i of myArray) {
        console.log(i);
    }
    /* a
     * b
     * c
     */
    ```
- `for...in`
  - `for (const x in y) {z}`의 꼴에서 `y`의 각 요소의 키(key)인 `x`를 순회하며 `z`를 반복한다.
    ```js
    let myObject = {first: 'apple', second: 'tomato', third: 'banana'};

    for (const i in myObject) {
        console.log(`${i} is ${myObject[i]}`);
    }
    /* first is apple
     * second is tomato
     * third is banana
     */
    ```

## while문

- `while`
  - `while(x) {y}`의 꼴에서 조건 `x`가 참인 동안 `y`를 반복한다.
- `do...while`
  - `do {x} while(y);`의 꼴에서 `x`를 한번 실행시킨 후, `y`가 참인 동안 `x`를 반복한다.
