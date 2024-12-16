# Java

- Hello, World!

  ```java
  public class HelloWorld {
      public static void main(String[] args) {
          System.out.println("Hello, World!");
      }
  }
  ```

- 주석(comments)

  ```java
  // single-line comments

  /*
  multi-line comments
  */
  ```

## 개발 환경(development environment)

- [`JDK`(Java Development Kit) 설치](./java/development_environment/jdk_setup.md)
- [`IDE`(Integrated Development Environment) 설치](../../application/ide/vscode/setup.md)

## 프로젝트(project)

- [프로젝트(project) 생성](./java/project/project_creation.md)
- [소스 코드(source code) 작성](./java/project/source_code_write.md)

## 기초

- [표준 출력](./java/basic/standard_out.md)
- [표준 입력](./java/basic/standard_in.md)
- [파일 입출력](./java/basic/file_io.md)
- [변수(variable)](./java/basic/variable.md)
- [자료형(type)](./java/basic/type.md)
- [연산자(operator)](./java/basic/operator.md)
- [값에 의한 호출과 참조에 의한 호출](./java/basic/call_by.md)

## 제어문(control statement)

- [반복문(iteration statement)](./java/statement/iteration.md)
- [조건문(conditional statement)](./java/statement/conditional.md)
- [루프 제어문(loop control)](./java/statement/loop_control.md)

## 클래스와 인터페이스

- [클래스(class)](./java/class.md)
- [인터페이스(interface)](./java/interface.md)
- 추상 클래스와 인터페이스의 비교
- [제네릭(generic)](./java/generic.md)
- 내장 클래스(built-in class)
  - [래퍼 클래스](./java/built_in_class/wrapper.md)
  - [API](./java/built_in_class/api.md)
- 컬렉션 프레임워크(collection framework)
  - [ArrayList](./java/collection_framework/arraylist.md)
  - [LinkedList](./java/collection_framework/linkedlist.md)
  - [HashSet](./java/collection_framework/hashset.md)
  - [HashMap](./java/collection_framework/hashmap.md)
- [열거체(enumerator)](./java/enumerator.md)

## 함수형 프로그래밍

- [함수형 인터페이스(functional interface)](./java/functional/functional_interface.md)
- [람다 표현식(lambda expression)](./java/functional/lambda_expression.md)
- [더블 콜론(double colon) 연산자](./java/functional/double_colon_operator.md)
- 스트림

## 스레드

- [`Thread` 클래스 상속](./java/thread/thread.md)
- [`Runnable` 인터페이스 구현](./java/thread/runnable.md)
- [`Executor` 프레임워크 사용](./java/thread/executor.md)
- [동기화 기법](./java/thread/synchronization.md)
- 데드락(교착 상태)
- 고급 스레드 관리 기법 (ForkJoinPool, CompletableFuture)

## 오류와 예외

- [오류와 예외(error and exception)](./java/exception/error_and_exception.md)
- [예외의 종류](./java/exception/exceptions.md)
- [예외 처리](./java/exception/try.md)

## OOP 디자인 패턴

<!-- TODO -->
