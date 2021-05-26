#启动mysql
docker run -d --name mysql -p 3306:3306 --restart=always -e TZ=Asia/Shanghai -e MYSQL_ROOT_PASSWORD=Abcd@123456 -v /home/docker/mysql:/var/lib/mysql mysql
