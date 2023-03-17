docker run --name envoy -v /etc/envoy/envoy.yaml:/ect/envoy/envoy1.yaml envoyproxy/envoy-alpine:v1.21-latest envoy -c /etc/envoy/envoy1.yaml


docker run  -it --rm -v /etc/envoy/test1:/etc/envoy  envoyproxy/envoy-alpine:v1.21-latest envoty --model validate -c /etc/envoy/envoy.yaml



docker run  -it --rm envoyproxy/envoy-alpine:v1.21-latest envoy --mode validate -c /etc/envoy/envoy.yaml


docker run  -d envoyproxy/envoy-alpine:v1.21-latest




##########################################################################################

envoy --mode validate -c /etc/envoy/envoy.yaml
docker run  -it --rm envoyproxy/envoy-alpine:v1.21-latest envoy --mode validate -c /etc/envoy/envoy.yaml
docker run -d envoyproxy/envoy-alpine:v1.21-latest envoy -c /etc/envoy/envoy.yaml


docker run  -it --rm -v /etc/envoy/test1/envoy1.yaml:/etc/envoy/envoy1.yaml  envoyproxy/envoy-alpine:v1.21-latest envoty --model validate -c /etc/envoy/envoy1.yaml
docker run  --rm -v F:\git\github\docker\envoy\envoy.yaml:/etc/envoy/envoy1.yaml  envoyproxy/envoy-alpine:v1.21-latest envoty --model validate -c /etc/envoy/envoy1.yaml

docker run  -d -v F:\git\github\docker\envoy\envoy.yaml:/etc/envoy/envoy1.yaml  envoyproxy/envoy-alpine:v1.21-latest envoty -c /etc/envoy/envoy1.yaml


###############################################################



