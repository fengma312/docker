docker run -d -p 8510:8500 --restart=always -v /XiLife/consul/data/server1:/consul/data -v /XiLife/consul/conf/server1:/consul/config -e CONSUL_BIND_INTERFACE='eth0' --privileged=true --name=consul_server_1 consul agent -server -bootstrap-expect=3 -ui -node=consul_server_1 -client='0.0.0.0' -data-dir /consul/data -config-dir /consul/config -datacenter=xdp_dc;


服务端启动：
consul agent -svrver -bootstrap-expect 1 -advertise-wan=183.11.37.73 -data-dir /tmp/consul -node  -bind=192.168.1.4 -ui client 0.0.0.0 -advertise=127.852.217.62

客户端启动：
consul agent -data-dir /tmp/consul -node=anll_12 -bind=192.168.1.4 -advertise=127.852.217.62 -client=0.0.0.0 -ui
 
服务端启动：
consul agent -server -advertise=127.852.217.62 -data-div /tmp/consul -node=tenxun -bind=192.168.1.4 -ui -client 0.0.0.0



sudo docker run -d --name consul1 consul  -bootstrap-expect 2  -bind=192.168.1.4 -ui -client 0.0.0.0








-----------------------好像可以使用-----------------------
服务端(领导)
consul agent -ui -server -bootstrap-expect 2 -data-dir /tmp/cocnsul -node=consul-server -bind=192.168.1.4 -client=192.168.1.4
服务端
consul agent -server -data-dir /tmp/consul -node=server2 -ui -bind=192.168.1.6 -join=192.168.1.4
客户端:
 consul agent -data-dir /tmp/consul -node c1 -bind=192.168.1.5  -join 192.168.1.6
------------------------------------------------------

sudo docker run -d -p 8300:8300 -p 8400:8400 -p 8500:8500 consul agent -server -ui -bootstrap-expect=2 -bind=192.168.1.4 -client=192.168.1.4