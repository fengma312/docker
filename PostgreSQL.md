#启动gpsql 用户名:postgres  密码:mypassword
sudo docker run -p 5432:5432 --restart=always --name pgsql -d -e POSTGRES_PASSWORD=mypassword -v /data/postgresql:/var/lib/postgresql/data  postgres