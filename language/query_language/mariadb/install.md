# 설치

## 설치 과정

1. MariaDB DBMS를 설치하기 위해 공식 홈페이지(`https://mariadb.org/`)에서 다운로드한다.
   - `MariaDB Server Version`: `MariaDB Server ?.?.?`의 형태로, 끝에 추가 문구가 없는 버전을 선택한다.
   - `Operating System`: `Windows`를 선택한다.
   - `Architecture`: `x86_64`를 선택한다.
   - `Package Type`: `MSI Package`를 선택한다. (권장) <2>로 이동
     > 만약, 기존에 설치된 프로그램을 유지한 상태로 추가 설치를 해야한다면, `ZIP file`을 선택한다. <3>으로 이동
2. 설치 과정에서 `root` 계정의 비밀번호를 설정한다. <4>로 이동
   - `root` 계정은 최고 권한의 계정이다.
3. <1>에서 다운로드 받은 압축 파일을 원하는 위치에 풀고, `bin` 디렉토리의 주소를 복사한다.
   - `명령 프롬프트`(혹은 `PowerShell`)에서 설치 위치로 이동하기 위해, 아래와 같이 명령한다.

     > ```ps
     > cd "<3>에서 복사한 주소"
     > ```
     >
     > 만약 <3>에서 복사한 주소가 `C:\dbms\bin` 라면, 명령어는 아래와 같다.
     >
     > ```ps
     > cd "C:\dbms\bin"
     > ```

   - 설치 위치로 이동했다면, MariaDB 설치를 위해 아래와 같이 명령한다.

     > ```ps
     > .\mysql_install_db.exe --service="서비스 이름" --port=포트번호 --password="root 계정 비밀번호"
     > ```
     >
     > 가령, 서비스 이름이 "CustomMariaDB"이고, 포트 번호가 "3306"이며, 초기 root 비밀번호가 "test1234"인 경우 아래와 같이 명령한다.
     >
     > ```ps
     > .\mysql_install_db.exe --service="CustomMariaDB" --port=3306 --password="test1234"
     > ```
     >
     > 정상적으로 설치되었다면 아래와 같이 출력된다.
     >
     > ```txt
     > Default data directory is C:\dbms\data
     > Running bootstrap
     > Registering service 'CustomMariaDB'
     > Creating my.ini file
     > Removing default user
     > Setting root password
     > Creation of the database was successful
     > ```

4. 서버의 인코딩을 `UTF8`로 변경해서 한글이 깨지지 않게 하기 위해 `MariaDB 설치 경로\data\my.ini` 파일을 메모장으로 열어 아래와 같이 내용을 추가/변경 한다.

     ```ini
     [mysqld]
     ...
     character-set-server=utf8
     [mysql]
     default-character-set=utf8
     [client]
     ...
     default-character-set=utf8
     ```

5. <4>에서 변경한 사항을 적용하기 위해 MariaDB 서비스를 재시작한다.
6. 환경변수로 등록해서 어느 경로에서든 접근할 수 있도록 한다.
   1. 키보드 `Win + R` 단축키를 사용해서 실행창을 연다.
   2. `sysdm.cpl ,3`을 입력해서 `시스템 속성`>`고급`으로 이동하고, `환경 변수`를 클릭한다.
   3. `시스템 변수`>`Path`를 선택하고, `편집`을 클릭한다.
   4. `새로 만들기`를 클릭하고, **bin** 폴더의 경로를 입력하고 확인을 클릭한다.
      - `MSI Package`를 통해 설치한다면, 기본 경로는 `C:\Program Files\MariaDB X.X\bin`의 꼴이다.

## 설치 확인

정상적으로 설치되었는지 확인하려면 다음 명령어를 입력한다.

> ```ps
> mysql --version
> ```
>
> 정상적으로 설치되었다면, `mysql.exe` 파일의 경로를 비롯한 버전정보가 출력된다.
>
> ```txt
> path\to\mysql.exe from ?.?.?-MariaDB, ...
> ```
