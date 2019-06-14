# Demonstrating Docker Context Switching

Pre-requisite:

- Docker Desktop Enterprise for Mac
- Docker 19.03 Beta 4

## Link: 

- [Context Switching](http://collabnix.com/docker-19-03-0-fast-context-switching-rootless-docker-sysctl-support-for-swarm-services/)


## Create a PWD Platform

```
sudo docker context create --docker host=tcp://ip172-18-0-5-biosq9o6chi000as1470.direct.labs.play-with-docker.com:2375 pwd-clu
ster1
```

## 

```
[:)Captain'sBay=>sudo docker context ls
NAME                DESCRIPTION                               DOCKER ENDPOINT                                                                 K
UBERNETES ENDPOINT                 ORCHESTRATOR
default *           Current DOCKER_HOST based configuration   unix:///var/run/docker.sock                                                     h
ttps://127.0.0.1:16443 (default)   swarm
pwd-cluster1   
```

