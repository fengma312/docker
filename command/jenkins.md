
docker run  -d -p 8099:8080 -p 50099:50000 --name jenkins -v E:\jenkins_home:/var/jenkins_home  jenkins/jenkins:lts


docker run --rm -u root -p 8080:8080 -v jenkins-data:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -v "$HOME":/home jenkinsci/blueocean

docker run   -u root   --rm   -d   -p 8080:8080   -p 50000:50000   -v jenkins-data:/var/jenkins_home   -v /var/run/docker.sock:/var/run/docker.sock   jenkinsci/blueocean
docker run   -d  -u root   -p 8080:8080  --name jenkins -v /jenkins_home:/var/jenkins_home   -v /var/run/docker.sock:/var/run/docker.sock   -v "$HOME":/home   jenkinsci/blueocean

docker run   -d  -u root   -p 8080:8080  --name jenkins -v /jenkins_home:/var/jenkins_home   -v /var/run/docker.sock:/var/run/docker.sock   -v "$HOME":/home   jenkins/jenkins


可以查看宿主机/usr/local/jenkins/secrets/initialAdminPassword文件获取密码。

029184c4131443c083f502f2ced51c14

jenkins URL:http://127.0.0.1:8099/
用户:root
密码:123456
全名:mf
电子邮件地址:fengma_312@126.com

