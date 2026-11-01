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

[hello-world 실습]

실행명령:
PS C:\codyssey> docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
4f55086f7dd0: Pull complete
d5e71e642bf5: Download complete
Digest: sha256:c567b231f65614688711a75f31518a064258a51d442117a3e771a3a8fdba78ef
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

 [ubuntu 에서 컨테이너 실행하기]

 실행명령:
 PS C:\codyssey> docker run -it --name ubuntu-practice ubuntu bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
f3f25b84a7d7: Pull complete
edafa32f5d9e: Pull complete
21594acc2d8b: Download complete
Digest: sha256:6a06111c3b0a8600feadb270aec771dc239bf407b25625f93f44ab00e11f4d3c
Status: Downloaded newer image for ubuntu:latest
ls
root@efd783e7b6e9:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@efd783e7b6e9:/# whoami
root
root@efd783e7b6e9:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@efd783e7b6e9:/# echo "Hello from Ubuntu container"
Hello from Ubuntu container
root@efd783e7b6e9:/# pwd
/
root@efd783e7b6e9:/# exit
exit

[DOCKERFILE을 작성해 웹 페이지 만들기]

1.Dockerfile 내용
2.docker build 명령어와 실행 결과
3.docker images 결과
4. docker run 명령어와 실행 결과
5. docker ps 결과
6. 브라우저에서 접속한 화면

