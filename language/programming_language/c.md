# C

- Hello, World!

  ```c
  #include <stdio.h>

  int main() {
      printf("Hello world!\n");
      return 0;
  }
  ```

- 주석(comments)

  ```c
  // single-line comments

  /*
  multi-line comments
  */
  ```

## 개발 환경(development environment)

- [컴파일러 설치](./c/compiler.md)
- [`IDE` 설치](../../application/ide/vscode/setup.md)

## 프로젝트(project)

- 프로젝트(project) 생성
- 소스 코드(source code) 작성

## 기초

- [원시 자료형(primivite type)](./c/basic/primitive_type.md)
- [변수와 상수(variable and constant)](./c/basic/variable.md)
- [표준 입출력](./c/basic/stdin.md)
- [파일 입출력](./c/basic/stdout.md)
- [연산자(operator)](./c/basic/operator.md)
  - 형승격(type promotion)
  - 형변환(type casting)
  - 쇼트 서킷(short circuit)

## 제어문(control statement)

- [반복문](./c/control/iteration.md)
- [조건문](./c/control/conditional.md)
- 흐름 제어문(flow control)
  - 레이블(label)
  - goTo
- 루프 제어문(loop control)
  - break
  - continue

## 자료형(type)

- 원시 자료형(primivite type)
- 파생 자료형(derived type)
  - 함수(function)
  - [배열(array)](./c/type/array.md)
  - [포인터(pointer)](./c/type/pointer.md)
- 사용자 정의 자료형(user defined type)
  - [구조체(struct)](./c/type/struct.md)
  - [공용체(union)](./c/type/union.md)
  - [열거체(enum)](./c/type/enum.md)

## 오류와 예외

- 오류와 예외
- 예외의 종류
- 예외 처리

## 스레드

- `Thread` 클래스 상속
- `Runnable` 인터페이스 구현
- `Executor` 프레임워크 사용
- 동기화 기법
- 데드락(교착 상태)
- 고급 스레드 관리 기법 (ForkJoinPool, CompletableFuture)

<!-- TODO -->
