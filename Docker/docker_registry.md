# Docker Private Registry 구축

## registry contianer 생성
```
docker pull registry
docker run -dit --name docker-registry -p 5000:5000 registry
```

## image 생성
```
docker build -t localhost:5000/container:latest .
```

## push my registry
```
docker push localhost:5000/container:latest
```

## registry에 이미지와 태그 리스트 확인하기
```
curl -X GET http://localhost:5000/v2/_catalog
curl -X GET http://localhost:5000/v2/container/tags/list
```

## in docker-compose
```
services:
  laravel:
    image: localhost:5000/container:latest
    ...
```
