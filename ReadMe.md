preview in vs code CTRL+K v

# Docker workshop

## Create app

* dotnet new webapi -o ArrowApi
* cd ArrowApi

## Run app

1. make changes to controller
2. remove https redirection
3. check webapi call

**dotnet run**

## Docker setup 

1. create docker file
2. create docker ignore file

### Docker build and run

* docker image build -t arrowapi:latest -f ./ArrowApi.dockerfile .
* docker run arrowapi:latest
* docker ps - no port exposed

### Docker expose port

* docker run -p 8080:80 arrowapi:latest
* http://localhost:80/arrow
* http://localhost:80/arrow/info?user=na

### Change aspnet port

* Uncomment ENV ASPNETCORE_URLS=http://+:5000
* docker image build -t arrowapi:latest -f ./ArrowApi.dockerfile .
* docker run -p 5000:5000 arrowapi:latest

https://stackoverflow.com/questions/48669548/why-does-aspnet-core-start-on-port-80-from-within-docker/48669703


* portainer localhost:9000 admin + password