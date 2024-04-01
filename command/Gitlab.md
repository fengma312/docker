https://docs.gitlab.com/ee/install/docker.html

企业版本  gitlab-ee 
开源版本 gitlab-ce  选择这个


sudo docker run --detach \
  --hostname gitlab.example.com \
  --env GITLAB_OMNIBUS_CONFIG="external_url 'http://gitlab.example.com'" \
  --publish 198.51.100.1:443:443 \
  --publish 198.51.100.1:80:80 \
  --publish 198.51.100.1:22:22 \
  --name gitlab \
  --restart always \
  --volume $GITLAB_HOME/config:/etc/gitlab \
  --volume $GITLAB_HOME/logs:/var/log/gitlab \
  --volume $GITLAB_HOME/data:/var/opt/gitlab \
  --shm-size 256m \
  gitlab/gitlab-ce:latest



sudo docker run --d \
  --hostname gitlab \
  --env GITLAB_OMNIBUS_CONFIG="external_url 'http://192.168.1.5'" \
  --env TZ="Asia/Shanghai"
  --publish 192.168.1.5:443:443 \
  --publish 192.168.1.5:80:80 \
  --publish 192.168.1.5:22:22 \
  --name gitlab \
  --restart always \
  --volume $GITLAB_HOME/config:/etc/gitlab \
  --volume $GITLAB_HOME/logs:/var/log/gitlab \
  --volume $GITLAB_HOME/data:/var/opt/gitlab \
  --shm-size 256m \
  gitlab/gitlab-ce:latest