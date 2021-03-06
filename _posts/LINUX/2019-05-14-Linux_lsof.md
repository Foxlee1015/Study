---
layout: post
title: Linux-lsof
categories: LINUX

---
* lsof

1. List Open File, 해당 시스템에서 구동되고 있는 Process 에 의해서 열려진 객체들을 확인 할 수 있는 명령어

2. 
- COMMAND : 프로세스 이름
- PID : 프로세스 ID
- USER : 사용자명
- FD : 파일 유형 ( cwd:현재 디렉토리, rtd:루트 디렉토리, txt:프로그램, mem:메모리 사상=기억장치의 내용을 다른 기억장치로 복사하는 것을 말하는데, 즉, -가상번지와 실번지를 대응시키는 것을 말한다.)
- TYPE : 파일과 관련된 유형 ( BLK:블록 특수 파일, CHR:문자 특수 파일, DIR:디렉토리, REG:일반 파일 )
- DEVICE : 장치에 대한 번호로서 "/dev" 하위에 있는 주번호,부번호를 의미
- SIZE : 파일의 크기를 의미한다. 즉, 옵셋을 의미
- NODE : 지역파일의 노드번호
- NAME : 객체 이름

---
> My raspberrypi
* $ lsof -i 
 - COMMAND    PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
 - gunicorn 18650   pi    5u  IPv4 136925      0t0  TCP *:5000 (LISTEN)
 - gunicorn 18651   pi    5u  IPv4 137518      0t0  TCP localhost:8000 (LISTEN)
 - gunicorn 18652   pi    5u  IPv4 137534      0t0  TCP *:5001 (LISTEN)
 - gunicorn 18655   pi    5u  IPv4 137518      0t0  TCP localhost:8000 (LISTEN)
 - gunicorn 18660   pi    5u  IPv4 137518      0t0  TCP localhost:8000 (LISTEN)
 - gunicorn 18661   pi    5u  IPv4 136925      0t0  TCP *:5000 (LISTEN)
 - gunicorn 18662   pi    5u  IPv4 137518      0t0  TCP localhost:8000 (LISTEN)
 - gunicorn 18663   pi    5u  IPv4 137534      0t0  TCP *:5001 (LISTEN)
 - gunicorn 18666   pi    5u  IPv4 137534      0t0  TCP *:5001 (LISTEN)
 - gunicorn 18667   pi    5u  IPv4 137534      0t0  TCP *:5001 (LISTEN)
* 8000: blog 5000: shop 5001: english

* 프로젝트가 supervisor 이 아닌 gunicorn 으로 가상환경에서만 돌아갈 경우
* kill -9 18667(PID), kill -9 18666 으로 해당 포트의 gunicorn 모두 중단한 후 sudo supervisorctl start english 로 다시 시작함 
