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
