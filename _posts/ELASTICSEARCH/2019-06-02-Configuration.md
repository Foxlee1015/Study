---
layout: post
title: Configuration
categories: ELASTICSEARCH

---

# 2019-06-02-AWS-ELK.md

* AWS 실행시 root(sudo su -) 에서 안됨 exit 으로 나간 후
 1. cd local/elastcisearch
 2. sudo bin/elsticsearch -d   = 계속 실행

3. curl -i http://localhost:9200/ 로 실행 확인 

1. root 로 접근하기  (sudo su )


https://okdevtv.com/mib/elk/elk6


* cp -r /dev/aaa /var/www/html/aaa 폴더 복사
* cp /dev/aaa /var/www/html/aaa 파일 복사



# 파이썬 3.6 설치 및 환경 설정
* https://wikidocs.net/16904

1. CentOS  - 파이썬 버전 확인 = python -version
2. yum update
3. yum groupinstall "Development Tools"             -> 안하면 configure 시 에러 
4. yum install wget
5. 파이썬 홈페이지 다운로드 링크 
6. wget 주소링크(확장자 tgz)
7. tar xvfz tgz파일  = 압축 풀기
8. 압축 푼 후 /etc 로 이동
9. Python3.6.8 안에서(configure이 있는 디렉토리에서)  ./configure 실행  = 설정 진행
10. make 설치 진행
11. python3 바로가기 만들기 = ln s /etc/Python3.6.8/python bin/python3   
12. python3 입력하여 설치 확인
13. 기존 파이썬 버전은 삭제시 오류발생하수 있으니 유지. 


* pip 오류 시 easy_install

- - -

# Nginx 설정

* 명령어
- sudo service nginx stop
- sudo service nginx reload
- sudo service nginx start

- sudo nano /etc/nginx/conf.d/virtual.conf  (Ip, html 설정 )


#
# A virtual host using mix of IP-, name-, and port-based configuration
#

    server {
        listen       8000;

        location / {
            root   html;
            index  index.html index.htm;
        }
    }


* Nginx - 
1. ps -ef | grep nginx   = nginx 가 정상적으로 구동중인지 파악
2. sudo netstat -ntip  포트 



* ufw 설치  (https://linuxconfig.org/how-to-install-and-use-ufw-firewall-on-linux)

 1. yum install epel-release -y (이미 설치 되어있었음)
 2. yum install --enablerepo="epel" ufw -y  // sudo su  - root 에서 
 3. sudoufw enable 


-ufw 돌아갈때 nigix 에 접속 안됨/ 포트설정은 AWS  index.html 안나오면 sudo ufw disable 

*


- - -
root에서
apt install openjdk-8-jdk-headless
(java -version, javac -version 둘다 확인)
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.1.1-amd64.deb (홈페이지에서 확인)


