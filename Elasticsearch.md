
启动es
docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:7.8.0

启动 kibana
docker run -d --name kibana --link elasticsearch:elasticsearch -p 5601:5601 kibana:7.8.0
启动 中文kibana
docker run -d --name kibana --link elasticsearch:elasticsearch -e "I18N_LOCALE=zh-CN" -p 5601:5601 kibana:7.8.0