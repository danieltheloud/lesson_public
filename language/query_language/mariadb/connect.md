# 접속

MariaDB 서버에 접속하기 위해 아래와 같이 명령한다.

```ps
mysql -u 사용자명 -p -P 포트번호
```

- `-u`는 접속하고자 하는 사용자의 이름을 지정하기 위해 사용한다.
- `-p`는 비밀번호를 이용하여 접속하겠다는 의미이다.
- `-P`는 접속하고자 하는 서버의 포트를 지정하기 위해 사용한다.
  - 생략할 경우, 기본 포트인 `3306`번 포트가 사용된다.

> 기본 포트에 root 계정으로 접속한다면, 명령어는 아래과 같다.
>
> ```ps
> mysql -u root -p
> ```

성공적으로 접속했다면 아래와 같이 명령줄이 변경된다.

```txt
Enter password: ********
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is ?
Server version: ?.?.?-MariaDB mariadb.org binary distribution
Copyright (c) yyyy, yyyy, Oracle, MariaDB Corporation Ab and others.
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
MariaDB [(none)]>
```
