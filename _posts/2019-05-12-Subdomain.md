---
layout: post
title: Subdomain
categories:
- blog
---
환경설정 //
virtualenv   // 다른 app 이 설치된 디렉토리에 가상환경 설정 - req.text , db 설정
gunicorn     // 포트 설정 gunicorn --bind 0.0.0.0:5000 run:app   ( 새로운 프로젝트의 앱 이름 run, 포트 5000에 올때 gunicorn 이 이 앱을 향함) 
supervisor   // 서버가 켜져있으면 python run.py or flask run 같이 실행하지 않아도 자동으로 켜짐(단, 라즈베리파이가 전원이 나갔다가 다시 켜지면 시스템 다시 작동시켜야함 -> sudo systemctl start nginx, 안되면 sudo systemctl stop apache2 후 다시. (아파치가 실행중일수 있음)