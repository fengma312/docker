https://docs.gitlab.com/ee/install/docker.html

企业版本  gitlab-ee 
开源版本 gitlab-ce  选择这个

//下面命令不要改任何东西   除了ip

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

-----------------------以下是安装 gitlab-runner ----------------注:如果出现验证失败，在/etc/gitlab-runner/config 下增加clone_url配置项 -------------------
https://docs.gitlab.com/runner/install/linux-manually.html
curl -L --output /usr/bin/gitlab-runner "https://s3.dualstack.us-east-1.amazonaws.com/gitlab-runner-downloads/latest/binaries/gitlab-runner-linux-amd64"
gitlab-runner install --user=root --working-directory=/root
chmod +x /usr/bin/gitlab-runner
gitlab-runner start
gitlab-runner register
gitlab-runner restart 

-------------------------------   以下是  .gitlab-ci.yml  示例 -----------------------  

before_script:
  - echo "global before script... "
after_script:
  - echo "global before after_script... "

stages:
  - job1
  - job2

job1:
  stage: job1
  before_script:
    - echo "job1 before_script... "
  script:
    - echo "job1 script... "
  after_script:
    - echo "job1 after_script... "
job2:
  stage: job2
  script:
    - echo "job2 script... "



----------------- 以下是 net 版本的 .gitlab-ci.yml  --------------------------

before_script:
  - echo "开始构建"
after_script:
  - echo "结束构建"

stages:
  - build
#  - deploy

job1:
  stage: build
  script:    
    - docker stop webapplication1
    - docker rm webapplication1
    - docker rmi webapplication1:latest
    - docker build -f ./WebApplication1/Dockerfile.debug -t webapplication1:latest .
    - docker run -d --name webapplication1 -p 8080:80 webapplication1:latest
