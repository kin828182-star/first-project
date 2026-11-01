# first-project
[권한 실습]

파일:
sample.txt

변경 전:
실제 ls -l 출력 결과
total 4
drwxr-xr-x 2 jay jay 4096 Oct 30 20:58 sample-dir
-rw-r--r-- 1 jay jay    0 Oct 30 20:58 sample.txt

실행 명령:
chmod 644 sample.txt

변경 후:
실제 ls -l 출력 결과
-rw-r--r-- 1 jay jay 0 Oct 30 20:58 sample.txt

추가 실습:
chmod 755 sample.txt
-rwxr-xr-x 1 jay jay 0 Oct 30 20:58 sample.txt

검증:
파일 권한이 644에서 755로 변경된 것을 확인했다.

[git 설치 및 설정하기]

실행 명령:
PS C:\Users\Jay> git config --global user.name
PS C:\Users\Jay> git config --global user.name "JAYYHON"
PS C:\Users\Jay> git config --global user.email "kin828182@gmail.com"
PS C:\Users\Jay> git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=schannel
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=JAYYHON
user.email=kin828182@gmail.com

[git 저장소 만들기]

실행 명령:
PS C:\Users\Jay> cd "$C\codyssey"
PS C:\codyssey> git init
Initialized empty Git repository in C:/codyssey/.git/
PS C:\codyssey> git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        codesample.html

nothing added to commit but untracked files present (use "git add" to track)
