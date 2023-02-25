

  docker run -p 9000:9000 -p 9001:9001 -d -e "MINIO_ACCESS_KEY=adminminio" -e "MINIO_SECRET_KEY=Ab$+cd1&234" -v /data/minio:/data -v /data/minio/config:/root/.minio --name minio --restart=always minio/minio server /data --console-address ":9001"
