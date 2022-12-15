# shell.cmd.powershell
Linux Shell, Windows Command, PowerShell 비교  

| shell                     | cmd                       | powershell      | 설명                                    |
|---------------------------|---------------------------|-----------------|-----------------------------------------|
| ls                        | dir                       | dir, ls, gci    | 현재 디렉토리 화일 목록보기             |
| ls -al                    |                           |                 |                                         |
| man ls                    | dir /?                    | man ls, man dir | ls 설명서보기, dir 설명서보기           |
| find . -name my.java      | dir my.java /s            |                 | 하위 디렉토리 포함하여 my.java화일 찾기 |
| env                       | set                       | gci env:        | 환경변수 보기                           |
| cd ..                     | cd ..                     | cd, sl          | 하위 디렉토리 이동                      |
| cd /                      | cd \                      | cd /, cd \      | 루트 디렉토리 이동                      |
| cd ~                      | cd %userprofile%          | cd ~            | 홈 디렉토리 이동                        |
| mkdir newdir              | mkdir newdir              | mkdir, ni       | newdir라는 디렉토리 만들기              |
| rmdir newdir              | rmdir newdir              | rmdir, ri       | newdir라는 디렉토리 삭제하기            |
| cat README.md             | type README.md            | cat, type, gc   | README.md라는 화일 내용물 보기          |
| cp README.md README2.md   | copy README.md README2.md | cp, copy, cpi   | 화일 복사하기                           |
| diff README.md README2.md | fc README.md README2.md   | diff, compare   | 화일내용물 비교하기                     |
| rm README2.md             | del README2.md            | rm, del, ri     | 화일 삭제하기                           |
