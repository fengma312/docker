docker run -d -e RABBITMQ_DEFAULT_USER=mquser -e RABBITMQ_DEFAULT_PASS=Abcd1234 -p 15672:15672 -p 5672:5672 --name mq --restart=always --hostname my-rabbit rabbitmq:management


docker run -d -p 5672:5672 --name mq --restart=always rabbitmq