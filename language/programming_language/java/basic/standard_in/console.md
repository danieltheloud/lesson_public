# Console 클래스

- `Console` 클래스는 `System.console` 메소드를 통해 접근하며, 콘솔 환경에서 사용자 입력을 처리하는 데 사용된다.
- **`GUI` 환경에서는 작동하지 않을 수 있음**에 유의한다.

```java
import java.io.Console;

public class Main {
    public static void main(String[] args) {
        Console console = System.console();

        if (console != null) {
            // 문자열 입력
            String str = console.readLine("Enter a string: ");

            // 비밀번호 입력 (에코 없음)
            char[] password = console.readPassword("Enter your password: ");

            System.out.println("String: " + str);
            System.out.println("Password: " + new String(password));
        } else {
            System.out.println("No console available.");
        }
    }
}
```

## Console 인스턴스 메소드

- `readLine`
  - `x.readLine(f, ...a)`의 꼴에서 포맷 문자열 `f`와 가변 인자 `a`을 출력하며, 입력받은 문자열을 반환한다.
- `readPassword`
  - `x.readPassword(f, ...a)`의 꼴에서 포맷 문자열 `f`와 가변 인자 `a`을 출력하며, 입력받은 문자열을 반환한다.
    - **입력 내용을 화면에 표시하지 않음**에 유의한다.
