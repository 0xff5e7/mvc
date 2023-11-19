Dockerfile
```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0
RUN git clone https://github.com/0xff5e7/mvc.git 
WORKDIR /mvc
CMD ["dotnet", "run", "--urls", "http://0.0.0.0:8000"]
```

run
```sh
docker build --no-cache -t myrror1 . && docker run -p 8000:8000 -p 9999:9999 myrror1
```

stop
```sh
docker ps -q --filter "ancestor=myrror1" | xargs docker stop
```
