# Docker 명령어 정리

## 참고

![docker-img](https://github.com/PAPION93/TIL/blob/master/img/docker-img.png)

## Docker image 리스트

`docker images`

## Docker image or Container 정보출력

`docker inspect [Container]`

## Dockerfile Build

`docker build [OPTIONS] PATH | URL | -`  
`docker build -t username/imagename:1.0 .`
> -d : Run container in the background  
> -t : Allocate a pseudo-tty
> -i : Keep STDIN open even if not attached

[Docker run reference](https://docs.docker.com/engine/reference/run/)

## docker image run

`docker run [OPTIONS] IMAGE`  
`docker run -dit --name container_name image`

## 컨테이너 시작

`docker start [Container]`

## 실행 중인 컨테이너에 로컬 표준 입력, 출력

`docker attach [Container]`

## 실행 중인 컨테이너에서 명령 실행

`docker exec -it [Container] /bin/bash`

## docker compose 실행, 다운

`docker-compose up -d [--build]`
> --build: image build  

`docker-compose down [-v]`  
> -v: 선언된 볼륨 제거  

## 호스트, 컨테이너간 파일 복사
### 컨테이너 -> 호스트  
`docker cp container:/root/data/test.md ~/data/ `

### 호스트 -> 컨테이너
`docker cp ~/data/test.md container:/root/data/`