# shell.cmd.powershell
Linux Shell, Windows Command, PowerShell 비교  

## File과 Directory관련 명령어

| shell                           | cmd                                    | powershell                                    | 설명                                    |
|---------------------------------|----------------------------------------|-----------------------------------------------|-----------------------------------------|
| ls                              | dir                                    | dir, ls, gci                                  | 디렉토리 화일 목록보기                  |
| ls -al                          |                                        |                                               |                                         |
| man ls                          | dir /?                                 | man ls, man dir                               | ls 설명서보기, dir 설명서보기           |
| find . -name my.java            | dir my.java /s                         |                                               | 하위 디렉토리 포함하여 my.java화일 찾기 |
| grep -rw . -e X923              | findstr /s /i X923 *.java              |                                               | "X923" 문자열이 있는 .java 화일 찾기    |
| pwd                             | cd                                     | pwd                                           | 현재 작업 디렉토리 보기                 |
| cd ..                           | cd ..                                  | cd, sl                                        | 하위 디렉토리 이동                      |
| cd /                            | cd \                                   | cd /, cd \                                    | 루트 디렉토리 이동                      |
| cd ~                            | cd %userprofile%                       | cd ~                                          | 홈 디렉토리 이동                        |
| mkdir newdir                    | mkdir newdir                           | mkdir, ni                                     | newdir라는 디렉토리 만들기              |
| rmdir newdir                    | rmdir newdir                           | rmdir, ri                                     | newdir라는 디렉토리 삭제하기            |
| cat README.md                   | type README.md                         | cat, type, gc                                 | README.md라는 화일 내용물 보기          |
| cp README.md README2.md         | copy README.md README2.md              | cp, copy, cpi                                 | 화일 복사하기                           |
| mv README2.md README3.md        | ren README2.md README3.md              | mv                                            | 화일명 변경하기                         |
| mv README2.md ..                |                                        | mv, mi                                        | 화일 이동                               |
| diff README.md README2.md       | fc README.md README2.md                | diff, compare                                 | 화일내용물 비교하기                     |
| rm README2.md                   | del README2.md                         | rm, del, ri                                   | 화일 삭제하기                           |
| which java                      | where java                             | gcm java                                      | 실행화일 java의 Full경로 얻기           |
| tail -f access.log              |                                        | gc -wait -tail 100 access.log                 | access.log 화일 TAIL 걸기               |
| chmod a+x gradlew               |                                        |                                               | gradlew 실행화일에 실행권한 주기        |
|                                 | attrib                                 |                                               | 화일 속성 보기                          |
|                                 | attrib +H .*                           |                                               | .으로 시작하는 화일을 숨김 화일로       |
| touch empty.txt                 | copy con empty.txt 후 &lt;Ctrl&gt;+'Z' |                                               | 0 크기 화일 만들기                      |
| touch empty.txt                 |                                        |                                               | empty.txt가 있으면 화일일자 갱신        |
| tar cvf newdir.tar newdir       | tar cvf newdir.tar newdir              | tar cvf newdir.tar newdir                     | 화일 묶기 (tape archive)                |
| tar tvf newdir.tar              | tar tvf newdir.tar                     | tar tvf newdir.tar                            | tar화일 내역 보기                       |
| tar xvf newdir.tar              | tar xvf newdir.tar                     | tar xvf newdir.tar                            | tar화일 풀기                            |
| gzip newdir.tar                 | tar cvfz newdir.tar.gz newdir          | tar cvfz newdir.tar.gz newdir                 | 화일 압축하기(.gz)                      |
| gunzip newdir.tar.gz            | tar xvf newdir.tar.gz                  | tar xvf newdir.tar.gz                         | 압축화일 풀기                           |
| wget http://www.abc.com/abc.zip | curl http://www.abc.com/abc.zip        | Start-BitsTransfer http://www.abc.com/abc.zip | 원격화일 가져오기                       |

참고> backup하기 [./backup.bat.md](./backup.bat.md)

## 네트워크 관련 명령어

| shell                          | cmd                                    | powershell                    | 설명                                    |
|--------------------------------|----------------------------------------|-------------------------------|-----------------------------------------|
| ifconfig                       | ipconfig                               | ipconfig                      | IP 보기                                 |
| hostname                       | hostname                               | hostname                      | Host Name 보기                          |
| traceroute 127.0.0.1           | tracert 127.0.0.1                      | tracert                       | 네트워크 경로 추적하기                  |
| ping 127.0.0.1                 | ping 127.0.0.1                         | ping 127.0.0.1                | ping 테스트 (IP에 접근가능 여부 Test)   |
| telnet 127.0.0.1 8080          | telnet 127.0.0.1 8080                  | telnet 127.0.0.1 8080         | telent 테스트 (Port 접근가능 여부 Test) |
| ssh 127.0.0.1                  | ssh user@127.0.0.1                     | ssh user@127.0.0.1            | ssh                                     |
| ftp 127.0.0.1                  | ftp 127.0.0.1                          | ftp 127.0.0.1                 | ftp                                     |
| sftp 127.0.0.1                 | sftp user@127.0.0.1                    | sftp user@127.0.0.1           | sftp                                    |
| nslookup localhost             | nslookup localhost                     |                               | DNS 테스트 (IP 얻기)                    |
| netstat -na &#124; grep LISTEN | netstat -na &#124; find "LISTEN"       |                               | Listen Port 확인하기                    |

## 환경 관련 명령어

| shell                          | cmd                                    | powershell                    | 설명                                    |
|--------------------------------|----------------------------------------|-------------------------------|-----------------------------------------|
| whoami                         | whoami                                 | whoami                        | 현 계정(User) 보기                      |
| uname -a                       | winver, systeminfo                     |                               | OS 버전 확인하기                        |
| env                            | set                                    | gci env:                      | 환경변수 보기                           |
| env &#124; grep PATH           | set PATH                               |                               | 환경변수 PATH 보기                      |
| locale, locale charmap         | chcp                                   |                               | console창 Charset(Code Page) 보기       |
|                                | chcp 65001                             |                               | console창 Charset을 UTF-8로             |
|                                | chcp 949                               |                               | console창 Charset을 EUC-KR로            |
| df -k                          | diskmgmt                               |                               | Disk 사용량 확인하기                    |

## Process 관련 명령어

| shell                          | cmd                                    | powershell                    | 설명                                    |
|--------------------------------|----------------------------------------|-------------------------------|-----------------------------------------|
| ps -ef &#124; grep java        | tasklist &#124; find "java"            |                               | 실행 되고 있는 java 프로그램 보기       |
| top                            | taskmgr                                |                               | CPU / Memory 사용량 보기                |
| kill                           | taskkill /pid                          |                               | PID(ProcessID)로 죽이기                 |


## 기타 명령어
| shell                          | cmd                                    | powershell                    | 설명                                    |
|--------------------------------|----------------------------------------|-------------------------------|-----------------------------------------|
| clear                          | cls                                    | clear, cls                    | console창 지우기                        |
| history                        | &lt;F7&gt;                             | history                       | 그동안 실행한 명령어 보기               |
| exit                           | exit                                   | exit                          | 종료하기                                |
| date                           | date, time                             | date                          | 현재날짜, 시간 보기                     |
| echo $PATH                     | echo %PATH%                            | echo $env:path                | 문자열 출력하기                         |
| cal                            |                                        |                               | 달력보기                                |
|                                | calc                                   |                               | 계산기 열기                             |
