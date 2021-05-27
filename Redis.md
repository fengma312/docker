#启动redis
sudo docker run -p 6379:6379 --restart=always --name redis  -d  -v /home/docker/redis/data:/data redis redis-server --appendonly yes  --requirepass "mypassword"

#启动redis 客户端
docker exec -it  redis redis-cli -h 192.168.1.80 -p mypassword