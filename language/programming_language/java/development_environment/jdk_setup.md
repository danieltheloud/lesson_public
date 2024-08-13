# JDK(Java Development Environment) 설치

## 설치 과정

1. 인터넷 브라우저를 통해서, 아래의 url로 접속한다.
   - `https://www.oracle.com/java/technologies/downloads/`
2. JDK는 최신 버전을 선택한다.
   - `JDK #`의 행태로, 추가 문구가 없는 버전을 선택한다.
3. 설치 OS에서 `Windows`를 선택한다.
   - 선택지는 `Linux`, `macOS`, `Windows`가 있다.
4. `x64 Installer`를 선택한다.
   - 다른 파일로도 설치가 가능하지만, 과정이 수월한 설치 프로그램을 사용한다.
5. 터미널을 열고, `java --version`이라고 입력해서 버전 정보가 정상적으로 출력되는지 확인한다.
   - 버전 정보는 아래와 비슷한 형태로 출력된다.
     ```
     java #.#.# yyyy-MM-dd
     Java(TM) SE Runtime Environment (build #.#.#)
     Java HotSpot(TM) 64-Bit Server VM (build #.#.#, mixed mode, sharing)
     ```

## 주의사항

- `JRE`가 아닌 `JDK`를 설치해야 한다.
  - `JRE`(Java Runtime Environment)는 자바 코드의 **실행 환경**을 제공하고, `JDK`(Java Development Kit)는 실행 환경과 더불어 컴파일러와 디버거까지 포함한 **개발 환경**을 제공한다.
- 만약, `JDK`를 설치하였음에도 불구하고, 버전 정보가 정상적으로 출력되지 않는다면, 환경 변수가 제대로 등록되지 않았을 가능성이 있다.
  1. `Win + R` 단축키를 입력하여, 실행창을 연다.
  2. `sysdm.cpl ,3`을 입력하여 `시스템 속성`>`고급`으로 이동하고, `환경 변수`를 클릭한다.
  3. `시스템 변수`>`Path`를 선택하고, `편집`을 클릭한다.
  4. `새로 만들기`를 클릭하고, **bin** 폴더의 경로를 입력하고 확인을 클릭한다.
     - `x64 Installer`를 통해 설치했다면, 경로는 `C:\Program Files\Common Files\Oracle\Java\javapath`이다.
