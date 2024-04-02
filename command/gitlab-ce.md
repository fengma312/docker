https://docs.gitlab.com/ee/install/docker.html

企业版本  gitlab-ee 
开源版本 gitlab-ce  选择这个

//下面命令不要改任何东西  

sudo docker run --detach \
  --hostname gitlab \
  --env GITLAB_OMNIBUS_CONFIG="external_url 'http://192.168.1.5'" \
  --env TZ="Asia/Shanghai"\
  --publish 443:443 \
  --publish 80:80 \
  --publish 222:22 \
  --name gitlab \
  --restart always \
  --volume /root/gitlab/config:/etc/gitlab \
  --volume /root/gitlab/logs:/var/log/gitlab \
  --volume /root/gitlab/data:/var/opt/gitlab \
  --shm-size 256m \
  gitlab/gitlab-ce:latest









  