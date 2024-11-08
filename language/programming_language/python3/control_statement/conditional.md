# 조건문

## if문

- `if`문은 `if`, `elif`, `else` 구문으로 구성되며, `if`를 제외한 나머지 구문은 선택사항이다.

```py
if condition1:
    # condition1이 참일 경우, 실행할 스코프
elif condition2:
    # condition2이 참일 경우, 실행될 스코프
else:
    # 모든 조건식이 거짓일 경우, 실행될 스코프
```

- 만약 각 구문에 실행해야할 코드가 한줄 뿐이라면 콜론 뒤에 연결하여서 작성이 가능하다.

```py
if condition1: # condition1이 참일 경우, 실행할 구문
elif condition2: # condition2이 참일 경우, 실행될 구문
else: # 모든 조건식이 거짓일 경우, 실행될 구문
```

## match문

> match문은 Python 3.10부터 도입된 구문으로, 여러 값의 패턴에 따라 코드 블록을 실행한다.

- `match`문은 타 언어의 `switch`문과 유사하다.
- `match`문은 변수나 표현식의 값을 검사하여, 일치하는 `case` 블록의 코드를 실행하는 방식으로 작동한다.
- `case _:`는 `default` 역할을 하며, 모든 case가 일치하지 않을 때 실행된다.
- **타 언어의 `switch`문과는 다르게, `break` 키워드를 사용하지 않아도, 해당 `case` 구문만 실행됨**에 유의한다.

```py
match variable:
    case value1:
        # variable의 값이 value1일 경우 실행할 구문
    case value2:
        # variable의 값이 value2일 경우 실행할 구문
    case _:
        # variable의 값이 모든 case가 일치하지 않을 경우 실행할 스코프
```

- 만약 각 구문에 실행해야할 코드가 한줄 뿐이라면 콜론 뒤에 연결하여서 작성이 가능하다.

```py
match variable:
    case value1: # variable의 값이 value1일 경우 실행할 구문
    case value2: # variable의 값이 value2일 경우 실행할 구문
    case _: # variable의 값이 모든 case가 일치하지 않을 경우 실행할 구문
```
