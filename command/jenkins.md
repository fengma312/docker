
docker run  -d -p 8099:8080 -p 50099:50000 --name jenkins -v E:\jenkins_home:/var/jenkins_home  jenkins/jenkins:lts

可以查看宿主机/usr/local/jenkins/secrets/initialAdminPassword文件获取密码。

029184c4131443c083f502f2ced51c14

jenkins URL:http://127.0.0.1:8099/
用户:root
密码:123456
全名:mf
电子邮件地址:fengma_312@126.com
