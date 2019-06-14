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

## Switch back to default 

```
[:)Captain'sBay=>sudo docker context ls
NAME                DESCRIPTION                               DOCKER ENDPOINT                                                                 K
UBERNETES ENDPOINT                 ORCHESTRATOR
default *           Current DOCKER_HOST based configuration   unix:///var/run/docker.sock                                                     h
ttps://127.0.0.1:16443 (default)   swarm
pwd-cluster1   
```

## Delete the PWD instances and try to recreate 3 Managers & 2 worker nodes

```
[Captains-Bay]🚩 >  docker context use pwd-cluster1
pwd-cluster1
Current context is now "pwd-cluster1"
[Captains-Bay]🚩 >  docker node ls
ID                            HOSTNAME            STATUS              AVAILABILITY        MANAGER STATUS      ENGINE VERSION
uc6wvd3nsm1xan0a5o874iovy     manager1            Ready               Active              Reachable           19.03.0-beta2
hz8klo3lirywordnhfy5in6dj     manager2            Ready               Active              Leader              19.03.0-beta2
ltpllqdnzp03lma8gb3f4a7kh *   manager3            Ready               Active              Reachable           19.03.0-beta2
os6vawxdhrx0a0be9it51syhz     worker1             Ready               Active                                  19.03.0-beta2
z2ipniffd9ifueplk6193bv6q     worker2             Ready               Active                                  19.03.0-beta2
[Captains-Bay]🚩 >  
```

## Clone the Wordpress Application Repository

```
git clone https://github.com/collabnix/dockerlabs
cd dockerlabs/solution/wordpress
```

```
docker stack deploy -c stack.yml myapp
```

Browse to PWD platform and see 8000 port appear.
