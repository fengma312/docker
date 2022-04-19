



docker run -p 9000:9000 -d -e "MINIO_ACCESS_KEY=admin_minio" -e "MINIO_SECRET_KEY=$Ab*cd12%34" -v /data/minio:/data --name minio --restart=always minio/minio server /data


docker run -p 9000:9000 -p 9001:9001 -d -e "MINIO_ACCESS_KEY=admin_minio" -e "MINIO_SECRET_KEY=$Ab*cd12%34" -v /data/minio:/data -v /data/minio/config:/root/.minio --name minio --restart=always quay.io/minio/minio server /data  --console-address ":9001"