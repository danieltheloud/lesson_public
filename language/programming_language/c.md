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

- [컴파일러(compiler) 설치](./c/compiler.md)
- [`IDE`(Integrated Development Environment) 설치](../../application/ide/vscode/setup.md)

## 프로젝트(project)

- 프로젝트(project) 생성
- 소스 코드(source code) 작성

## 기초

- 자료형
- 변수와 상수
- 표준 입출력
- 파일 입출력
- 자료형(type)
- [연산자(operator)](./c/basic/operator.md)
  - 형승격(type promotion)
  - 형변환(type casting)
  - 쇼트 서킷(short circuit)

## 제어문(control statement)

- 반복문(iteration statement)
- 조건문(conditional statement)
- 루프 제어문(loop control)

## 클래스와 인터페이스

- 클래스(class)
- 인터페이스(interface)
- 추상 클래스와 인터페이스의 비교
- 제네릭(generic)
- 내장 클래스(built-in class)
  - 래퍼 클래스
  - API
- 컬렉션 프레임워크(collection framework)
  - ArrayList
  - LinkedList
  - HashSet
  - HashMap
- 열거체(enumerator)

## 함수형 프로그래밍

- 함수형 인터페이스(functional interface)
- 람다 표현식(lambda expression)
- 더블 콜론(double colon) 연산자
- 스트림

## 스레드

- `Thread` 클래스 상속
- `Runnable` 인터페이스 구현
- `Executor` 프레임워크 사용
- 동기화 기법
- 데드락(교착 상태)
- 고급 스레드 관리 기법 (ForkJoinPool, CompletableFuture)

## 오류와 예외

- 오류와 예외
- 예외의 종류
- 예외 처리

## OOP 디자인 패턴

<!-- TODO -->
