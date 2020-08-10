# Docker Private Registry 구축

## registry contianer 생성

```
docker pull registry
docker run -dit --name docker-registry -p 5000:5000 registry
```

## image 생성

```
docker build -t localhost:5000/hello-world:latest .
```

## push my registry

```
docker push localhost:5000/hello-world:latest
```

## in docker-compose

```
services:
  laravel:
    image: localhost:5000/hello-world:latest
    ...
```
