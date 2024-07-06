# Backup화일 만들기
## tar.gz화일 [ Windows 10과 Linux(Unix) 공통용]

- backup.bat
  ```cmd
  @echo off

  for /f "usebackq delims=" %%a in (`
  powershell -c "$dt = Get-Date ; $dt.ToString('yyyyMMddHHmmss')"
  `) do set "YYYYMMDDHHMMSS=%%a"

  set YYYYMMDD=%YYYYMMDDHHMMSS:~0,8%
  set HHMM=%YYYYMMDDHHMMSS:~8,4%
  set ZIP_NAME=..\source.%YYYYMMDD%.%HHMM%.tar.gz

  tar cvfz %ZIP_NAME% *.h *.c *.cpp ^
  *.dsw ^
  *.sln

  echo
  echo %ZIP_NAME% create
  echo tar tvf %ZIP_NAME%

  ```
- backup.sh
  ```shell
  #!/bin/sh
  
  YYYYMMDD=`date +%Y%m%d`
  HHMM=`date +%H%M`
  ZIP_NAME=../source.%YYYYMMDD%.%HHMM%.tar.gz
  
  tar cvfz ${ZIP_NAME} *.h *.c *.cpp \
  *.dsw \
  *.sln
  
  echo ""
  echo "${ZIP_NAME} create"
  echo "tar tvf ${ZIP_NAME}"
  ```

## jar로 .zip화일 만들기 (java 또는 kotlin개발 환경)

- backup.bat
  ```cmd
  @echo off

  for /f "usebackq delims=" %%a in (`
  powershell -c "$dt = Get-Date ; $dt.ToString('yyyyMMddHHmmss')"
  `) do set "YYYYMMDDHHMMSS=%%a"

  set YYYYMMDD=%YYYYMMDDHHMMSS:~0,8%
  set DIR_NAME=soruce
  set ZIP_NAME=%DIR_NAME%.%YYYYMMDD%.zip

  cd ..
  
  jar cvfM %ZIP_NAME% ^
  %DIR_NAME%/demo/*.js ^
  %DIR_NAME%/demo/*.html ^
  %DIR_NAME%/demo/*.apk ^
  %DIR_NAME%/backup.* ^
  %DIR_NAME%/package.json ^
  %DIR_NAME%/*.md
  
  cd %DIR_NAME%
  
  echo make ..\%ZIP_NAME%
  echo jar tvf ..\%ZIP_NAME%

  ```
- backup.sh
  ```shell
  #!/bin/sh
  
  YYYYMMDD=`date +%Y.%m.%d`
  DIR_NAME=source
  ZIP_NAME=${DIR_NAME}.${YYYYMMDD%}.zip
  
  cd ..
  
  jar cvfM ${ZIP_NAME} \
  ${DIR_NAME}/demo/*.js \
  ${DIR_NAME}/demo/*.html \
  ${DIR_NAME}/demo/*.apk \
  ${DIR_NAME}/backup.* \
  ${DIR_NAME}/package.json \
  ${DIR_NAME}/*.md
  
  cd ${DIR_NAME}
  
  echo ""
  echo "make ../${ZIP_NAME}"
  echo "jar tvf ../${ZIP_NAME}"
  ```
