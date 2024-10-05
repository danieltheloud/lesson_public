# 프로젝트 생성

## 프로젝트 생성 과정

1. `Ctrl + Shift + P` 단축키를 입력하여 `커맨드 팔레트`(command palette)를 연다.
2. `Java: Create Java Project...`를 입력한다.
   - "language"만 입력하고, 하단에 드롭다운된 항목에서 선택한다.
3. `No build tools`를 선택한다.
4. 프로젝트를 설치할 경로를 선택한다.
5. 프로젝트명을 지어준다.
   - 프로젝트의 이름은 `파스카 케이스`(Pascal Case)로 작성하는 것이 일반적이다.

## 프로젝트 구조

- 프로젝트를 생성하면 기본적으로 `bin`, `lib`, `src`라는 이름의 폴더들이 생성된다.
- `src`(source) 폴더는 개발자가 `*.java` 꼴의 `소스 코드`(source code)를 직접 작성하는 경로이다.
- `bin`(binary) 폴더는 `*.class` 꼴의 `바이너리 파일`(binary file)이 컴파일(compile)되는 경로이다.
- `lib`(library) 폴더는 의존성(dependency)으로 추가할 `*.jar` 꼴의 파일을 저장하는 경로이다.
