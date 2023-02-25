#启动asp.net core 运行
sudo docker run  -d  -p 80:80  --restart=always -e TZ=Asia/Shanghai -v /home/github/test/bin/publish/netcoreapp3.1/publish/:/app  -w /app  mcr.microsoft.com/dotnet/core/aspnet  dotnet /app/test.dll

#启动dotnet 发布
sudo docker run  --name publish_worker -v /home/github/:/app -w /app mcr.microsoft.com/dotnet/core/sdk dotnet publish  -c Release RobotTrading/Com.Worker/

#启动asp.net core
docker run -d -p 8081:80 --restart=always  --name coin  -e TZ=Asia/Shanghai -v /data/github/RobotTrading/Com.Web/bin/Release/netcoreapp3.1/publish/:/app -w /app mcr.microsoft.com/dotnet/core/aspnet dotnet Com.Web.dll
