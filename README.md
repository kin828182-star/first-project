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

1.Dockerfile 내용:
PS C:\codyssey> notepad Dockerfile
PS C:\codyssey> get-content Dockerfile
FROM nginx:latest

COPY app/index.html /usr/share/nginx/html/index.html

EXPOSE 80

2.docker build 명령어와 실행 결과:
PS C:\codyssey> docker build -t coding-mission-web:1.0 .
[+] Building 8.4s (8/8) FINISHED                                                                   docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                               0.0s
 => => transferring dockerfile: 123B                                                                               0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                    2.4s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                       0.0s
 => [internal] load .dockerignore                                                                                  0.0s
 => => transferring context: 2B                                                                                    0.0s
 => [internal] load build context                                                                                  0.1s
 => => transferring context: 366B                                                                                  0.0s
 => [1/2] FROM docker.io/library/nginx:latest@sha256:5ab5b0b01097420873a3f3330f44248e34a3c2a3e8d5ee30658aeae8cb74  3.8s
 => => resolve docker.io/library/nginx:latest@sha256:5ab5b0b01097420873a3f3330f44248e34a3c2a3e8d5ee30658aeae8cb74  0.0s
 => => sha256:a670537bed7086aeb8b663aad5e09cd584e19c6598cd2b6d905c5f2f2513938b 1.40kB / 1.40kB                     0.2s
 => => sha256:d322f1bf41d8e99dc47f550cbf85e79ca18bc45db12fd1b7a8b34bf79cbd7d5a 1.21kB / 1.21kB                     0.4s
 => => sha256:c139fe92686de21a8c49d9cb40415d1dddd95fbbee4d696cebe37693236fe6d4 404B / 404B                         0.6s
 => => sha256:6e2ab1f3ef4e0ea3bbe1d208dfa048969199e3dab99e93c051b7c2d09c8efb3e 964B / 964B                         0.6s
 => => sha256:9f604dae09b216f6c87919d0e59d5a4ddc4387ef071cf63c645628f93808e37b 628B / 628B                         0.4s
 => => sha256:a071113ac575190a0fee0c046bcf51632356f07419bdffaa55798f54e5b2e23b 34.05MB / 34.05MB                   1.9s
 => => sha256:6fc242d221a673263eabd14a9ad9584d3177c96e5cb504c891497338e2f912f5 29.86MB / 29.86MB                   1.4s
 => => extracting sha256:6fc242d221a673263eabd14a9ad9584d3177c96e5cb504c891497338e2f912f5                          0.8s
 => => extracting sha256:a071113ac575190a0fee0c046bcf51632356f07419bdffaa55798f54e5b2e23b                          0.6s
 => => extracting sha256:9f604dae09b216f6c87919d0e59d5a4ddc4387ef071cf63c645628f93808e37b                          0.0s
 => => extracting sha256:6e2ab1f3ef4e0ea3bbe1d208dfa048969199e3dab99e93c051b7c2d09c8efb3e                          0.0s
 => => extracting sha256:c139fe92686de21a8c49d9cb40415d1dddd95fbbee4d696cebe37693236fe6d4                          0.0s
 => => extracting sha256:d322f1bf41d8e99dc47f550cbf85e79ca18bc45db12fd1b7a8b34bf79cbd7d5a                          0.0s
 => => extracting sha256:a670537bed7086aeb8b663aad5e09cd584e19c6598cd2b6d905c5f2f2513938b                          0.0s
 => [2/2] COPY app/index.html /usr/share/nginx/html/index.html                                                     0.1s
 => exporting to image                                                                                             1.8s
 => => exporting layers                                                                                            0.1s
 => => exporting manifest sha256:457de8294cfe873d4718c51128e306b377f69b6676d00a6201ae83dc3fa298ca                  0.0s
 => => exporting config sha256:1f947fc378beb6b47984a5f0d3a25aa150beafba957f45561cfaa3c8b1a0c31c                    0.0s
 => => exporting attestation manifest sha256:153fe9337334daf815ba74263257214e9e4058cc5ffe3425e04f0736f1f38478      0.0s
 => => exporting manifest list sha256:83e730c96e63f0642b0202082b866a1cba66863d3d6e5f041b9eb73a3932ab36             0.0s
 => => naming to docker.io/library/coding-mission-web:1.0                                                          0.0s
 => => unpacking to docker.io/library/coding-mission-web:1.0                                                       1.5s
 
3.docker images 결과:
PS C:\codyssey> docker images
                                                                                                   i Info →   U  In Use
IMAGE                    ID             DISK USAGE   CONTENT SIZE   EXTRA
coding-mission-web:1.0   83e730c96e63        241MB         63.9MB
hello-world:latest       c567b231f656       25.9kB         9.49kB    U
ubuntu:latest            6a06111c3b0a        163MB         45.9MB    U

4. docker run 명령어와 실행 결과:
PS C:\codyssey> docker run -d --name coding-web -p 8080:80 coding-mission-web:1.0
1e80d9df4467ae62d1a2d15ccc669dcd8ef37b2acf1a7d98c4203817f6888fd1

6. docker ps 결과:
PS C:\codyssey> docker ps
CONTAINER ID   IMAGE                    COMMAND                   CREATED          STATUS          PORTS                                     NAMES
1e80d9df4467   coding-mission-web:1.0   "/docker-entrypoint.…"   18 seconds ago   Up 17 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   coding-web

8. 브라우저에서 접속한 화면: 이미지 첨부 불가
