---
layout: post
title: MYSQL_1
categories:
- blog
---




[참고1]:


* mysql 서버 설정
  * sudo apt-get install mysql-server
  * sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
    * bind-address = 127.0.0.1 -->> 0.0.0.0 으로 수정  (주석 제거)
  * mysql port 허용 - sudo ufw 3306

  * mysql 접속
    1. mysql -uroot -p
    2. use mysql
    3. 서버에 접속할 클라이언트단 정보 설정하기
    4. insert into user (host, user, password) values ('서버에 접속할 ip 주소', '서버 접속시 사용할 user 이름', password('*******'));
    5. insert into db values('서버에 접속할 ip 주소', '서버 mysql에서 db 선택','서버 접속시 허용되는 user 이름' ,'y','y','y','y','y','y','y','y','y','y','y','y','y','y','y','y','y', 'y', 'y');  // 기타 사항 y 로 허용
    6. 설정 완료 후 flush privileges; / exit 
    7. sudo service mysql restart
  * 기타 설정사항은 desc user, desc db 로 확인 가능 
    
    
![20190818_174322](https://user-images.githubusercontent.com/47915302/63222222-cb0ceb00-c1df-11e9-816a-505106879f64.png)
![20190818_174341](https://user-images.githubusercontent.com/47915302/63222223-cc3e1800-c1df-11e9-9dd4-da0097bc78bc.png)


* 클라이언트 설정
    
    
    
         /main.py
        def connect():
           return pymysql.connect(host='서버에 접속할 ip 주소(이 파일이 작성되는 곳의 ip)', user='daehan', password='*****', db='users', charset='utf8')
        상단에서 설정한 서버에 접속시 허용되는 user 이름 = daehan, 해당 user가 접근 가능한 db는 users 라는 database, 

        def select_data():
           conn = connect()
           try:
               curs = conn.cursor(pymysql.cursors.DictCursor)
               sql = """select * from user_list order by uid"""
               curs.execute(sql)
               row = curs.fetchall()
               print(row)
               return row
           except Exception as e:
               print(e)
               return None
           finally:
               conn.close()





[참고1]:http://faq.hostway.co.kr/Linux_DB/1286
