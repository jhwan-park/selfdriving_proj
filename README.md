파일 전송법

1. 라즈베리파이와 노트북 동일 네트워크 접속
2. window powershell 관리자권한으로 접속
명령어 ssh pjh@(ipaddress ex.172.20.10.7)
명령어 exit
C 경로 줄줄이 나오면 명령어 cd/ 입력
C :\ 나오는지 확인
명령어 scp "옮기려는 파일경로" pjh@172.20.10.7:~/원하는 파일경로
(ex. scp "C:\python_practice\py_CNN\CNNtest.py" pjh@172.20.10.7:~/project/)
라즈베리파이에서 확인
