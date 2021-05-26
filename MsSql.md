# 启动mssql
docker run -d --name mssql -p 1433:1433 --restart=always -e TZ=Asia/Shanghai -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=Abcd@123456' -v mssql:/var/opt/mssql/ mcr.microsoft.com/mssql/server