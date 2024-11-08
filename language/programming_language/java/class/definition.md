# 클래스 정의

- 클래스는 객체를 정의하는 청사진으로, 객체의 상태와 행동을 지정하는 필드(field)와 메소드(method)로 구성된다.
- `a class n {}`의 꼴에서 `a`는 접근 제한자, `n`은 클래스의 이름이다.
- **하나의 파일 내에는 하나의 `public` 클래스만 존재해야 함**에 유의한다.
  - 유지보수를 위해서, 하나의 파일에는 하나의 클래스만 작성하는 것이 좋다.
- 명명법: `파스칼 케이스`

```java
public class MyClass {
    // 필드 및 메소드
}
```

## 접근 제한자

- `public`: 클래스 외부에서도 접근이 가능하다.
- `protected`: 같은 패키지 내에서 또는 상속 관계에서 접근이 가능하다.
- `private`: 해당 클래스 내에서만 접근이 가능하다.
  - 내부의 정보를 은닉하여 보안성을 높이기 위해서 자주 사용된다.

## 필드

- 필드는 클래스 내에 선언된 변수로, 객체의 속성을 정의한다.
- 명명법: `카멜 케이스`

### 인스턴스 필드

- `인스턴스 필드`는 클래스의 **각 인스턴스에 고유하게 존재**하는 필드이다.
- **객체가 생성될 때마다 독립적으로 할당**되며, 인스턴스마다 별도의 값을 갖는다.

```java
public class MyClass {
    private int instInt;
    private String instString;
}
```

### 정적 필드

- `정적 필드`는 클래스에 하나만 존재하며, **모든 인스턴스가 공유**한다.
- `static` 키워드를 사용하여 선언한다.

```java
public class MyClass {
    private static int staticInt;
}
```

## 메소드

- 메소드는 클래스의 동작(기능)을 정의하며, 특정 작업을 수행하는 코드 블록이다.
- 명명법: `카멜 케이스`

### 생성자 메소드

- 생성자는 `new` 키워드와 함께 객체가 생성될 때 자동으로 호출되며, **클래스 이름과 동일한 이름**을 가진 메소드이다.
- 객체 초기화에 사용된다.
  - **반환 자료형이 없음**에 유의한다.

```java
public class MyClass {
    private int instInt;

    public MyClass(int instInt) {
        this.instInt = instInt;
    }
}
```

### 인스턴스 메소드

- `인스턴스 메소드`는 특정 객체의 상태를 조작하거나 반환한다.
- 생성된 인스턴스로부터 `맴버 접근 연산자`를 사용해 호출할 수 있다.

```java
public class MyClass {
    private int instInt;

    public void setInstInt(int instInt) {
        this.instInt = instInt;
    }

    public int getInstInt() {
        return this.instInt;
    }
}
```

### 정적 메소드

- `정적 메소드`는 클래스에 속하며, 클래스 이름으로 직접 호출할 수 있다.
- `인스턴스 필드`에 접근하지 못하며, `정적 필드`나 `정적 메소드`만 사용할 수 있다.

```java
public class MyClass {
    private static String name = "John";

    private static String myStaticFunc1() {
        return String.format("My name is %s.", name);
    }

    public static void myStaticFunc2() {
        System.out.println(myStaticFunc1());
    }
}
```
