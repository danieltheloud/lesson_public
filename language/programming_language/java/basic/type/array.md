# 배열

- `Java`의 배열은 동일한 자료형끼리 모아놓은 일련의 자료형이다.

## 배열 자료형의 선언

- `T[] v`의 꼴에서 변수명이 `v`이고, 요소의 자료형이며 `T`인 변수를 선언한다.
  - `T v[]`의 꼴로 표현할 수도 있지만, `T[] v`의 꼴로 작성하는 것이 더 일반적이다.
- 배열은 고정 길이의 자료형으로써, **초기화하지 않고 선언만 해서는 사용할 수 없음**에 유의한다.

  ```java
  int[] numbers;
  ```

## 배열 자료형의 초기화 및 할당

> 배열 변수를 초기화할 때, 배열 상수나 생성자를 사용할 수 있다.
>
> 배열 변수를 할당할 때, 배열 생성자를 사용할 수 있다.

- 배열 상수
  - 배열 상수는 중괄호(`{`, `}`)로 감싸고, 요소들을 쉼표(`,`)로 구분해서 표현한다.
  - **배열 변수를 할당할 때는 배열 상수를 사용할 수 없음**에 유의한다.

  ```java
  // 배열 상수를 사용한 초기화
  int[] numbers = {1, 2, 3, 4, 5};
  ```

- 배열 생성자
  - `new T[x]`의 꼴에서 길이가 `x`이고 자료형이 `T`인 배열을 할당한다.

  ```java
  // 길이가 5인 빈 정수형 배열 생성
  int[] numbers = new int[5];
  ```

## 배열 순회

- `전통적인 for문`과 `향상된 for문`을 사용해 배열의 각 요소를 순회할 수 있다.

  ```java
  // 전통적인 for문
  for (int i = 0; i < numbers.length; i++) {
      System.out.println(numbers[i]);
  }

  // 향상된 for문
  for (int number : numbers) {
      System.out.println(number);
  }
  ```

## 배열의 요소 접근

- 배열의 각 요소는 인덱스를 통해 접근할 수 있다.
- 배열 인덱스는 `0`부터 시작하며, 마지막 인덱스는 `배열 길이 - 1`이 된다.
- 배열 요소 값은 인덱스를 사용해 수정할 수도 있다.

  ```java
  int[] numbers = {1, 2, 3, 4, 5};
  System.out.println(numbers[0]);                   // 1
  System.out.println(numbers[numbers.length - 1]);  // 5
  ```

## 배열의 속성

- `length`
  - 배열의 길이를 나타내는 속성으로, 배열에 저장된 요소의 총 개수를 반환한다.

  ```java
  System.out.println(numbers.length);
  ```

## Arrays 스태틱 메소드

- `Arrays.toString`
  - `Arrays.toString(x)`의 꼴에서 배열 `x`의 각 원소를 쉼표로 구분하고 대괄호로 감싸서 문자열로 반환한다.
- `Arrays.sort`
  - `Arrays.sort(x)`의 꼴에서 배열 `x`의 각 원소를 오름차 정렬한다.
  - `Arrays.sort(x, y)`의 꼴에서 배열 `x`의 각 원소를 함수 `y`에 따라 정렬한다.
    - `x`가 원시 자료형 배열이라면, `래퍼 클래스`로 바꿔줘야 한다.
- `Arrays.copyOf`
  - `Arrays.copyOf(x)`의 꼴에서 배열 `x`를 깊은 복사해서 반환한다.

## 다차원 배열

- 대괄호를 사용한 회수에 따라서 다차원 배열을 사용할 수 있다.

  ```java
  // 배열 상수를 사용한 초기화
  int[][] numberArrays1 = {
      {1, 2, 3},
      {4, 5, 6},
      {7, 8, 9}
  };

  // 길이가 3*3인 빈 정수형 배열 생성
  int[][] numberArrays2 = new int[3][3];
  ```
