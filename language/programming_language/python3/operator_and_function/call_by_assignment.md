# 대입에 의한 호출(call by assignment)

- `Python`은 `대입에 의한 호출`(call by assignment) 또는 더 일반적으로 `객체 참조에 의한 호출`(call by object reference) 방식을 사용한다.
  - 이는 다른 프로그래밍 언어에서 사용되는 `값에 의한 호출`(call by value)이나 `참조에 의한 호출`(call by reference)과는 다르다.
- `Python`의 대입에 의한 호출을 이해하려면 다음 두 가지 중요한 개념을 알아야 한다.

  > 1. 모든 것은 객체(everything is an object)이다.
  >    - `Python`에서 숫자, 문자열, 리스트, 함수 등 모든 것은 객체이다.
  >    - 변수는 이러한 객체에 대한 참조(reference)를 저장한다.
  > 2. 가변(`mutable`) 객체와 불변(`immutable`) 객체
  >    - 불변 객체: 생성된 후에는 그 값을 변경할 수 없는 객체이다.
  >    - 가변 객체: 생성된 후에도 그 내용을 변경할 수 있는 객체이다.

## 대입에 의한 호출(call by assignment)의 작동 방식

- 함수에 인자를 전달할 때, `Python`은 변수가 참조하고 있는 객체의 참조를 복사하여 함수 내부의 매개변수에 대입한다.
  - 불변 객체를 전달할 경우:

    > - 함수 내부에서 매개변수에 새로운 값을 대입하면, 이는 원래 객체를 변경하는 것이 아니라 매개변수가 새로운 객체를 참조하게 만든다.
    >   - 원래 변수는 여전히 원래 객체를 참조한다.
    > - 따라서 함수 외부의 원본 변수에는 영향을 미치지 않다.
    >
    > ```py
    > def modify_number(num):
    >     print(f"대입 전: num의 id = {id(num)}, num = {num}")
    >     num = num + 10  # num이 새로운 객체를 참조
    >     print(f"대입 후: num의 id = {id(num)}, num = {num}")
    >
    > my_number = 5
    > print(f"함수 호출 전: my_number의 id = {id(my_number)}, my_number = {my_number}")
    > modify_number(my_number)
    > print(f"함수 호출 후: my_number의 id = {id(my_number)}, my_number = {my_number}")
    > ```
    >
    > ```
    > 함수 호출 전: my_number의 id = (원래의 id), my_number = 5
    > 대입 전: num의 id = (원래의 id), num = 5
    > 대입 후: num의 id = (새로운 id), num = 15
    > 함수 호출 후: my_number의 id = (원래의 id), my_number = 5
    > ```

  - 가변 객체를 전달할 경우:

    > - 함수 내부에서 매개변수가 참조하는 객체의 속성(attribute)과 메소드(method)를 변경하면, 이는 원본 객체를 직접 변경하는 것이다.
    >   - 따라서 함수 외부의 원본 변수도 변경된 내용을 반영한다.
    >
    > ```py
    > def modify_list_content(my_list):
    >     print(f"메소드 호출 전: my_list의 id = {id(my_list)}, my_list = {my_list}")
    >     my_list.append(4)  # 리스트 객체의 내용 변경
    >     print(f"메소드 호출 후: my_list의 id = {id(my_list)}, my_list = {my_list}")
    >
    > my_original_list = [1, 2, 3]
    > print(f"함수 호출 전: my_original_list의 id = {id(my_original_list)}, my_original_list = {my_original_list}")
    > modify_list_content(my_original_list)
    > print(f"함수 호출 후: my_original_list의 id = {id(my_original_list)}, my_original_list = {my_original_list}")
    > ```
    >
    > ```txt
    > 함수 호출 전: my_original_list의 id = (원래의 id), my_original_list = [1, 2, 3]
    > 메소드 호출 전: my_list의 id = (원래의 id), my_list = [1, 2, 3]
    > 메소드 호출 후: my_list의 id = (원래의 id), my_list = [1, 2, 3, 4]
    > 함수 호출 후: my_original_list의 id = (원래의 id), my_original_list = [1, 2, 3, 4]
    > ```
    >
    > - 하지만 함수 내부에서 매개변수 자체에 새로운 객체를 대입하면, 이는 매개변수가 새로운 객체를 참조하게 만들 뿐, 원본 변수에는 영향을 주지 않다.
