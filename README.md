# swarm-tutorial

## SERVICES. -- docker service --

### CREATE

`docker service create` creates a service

`docker service create --name nginx --replicas 5 --publish 8080:80 nginx`

create, name, amount of containers, cluster_port:each_container_port, docker_image_name

**First creation output**

```
1/5: running   [==================================================>] 
2/5: running   [==================================================>] 
3/5: running   [==================================================>] 
4/5: running   [==================================================>] 
5/5: running   [==================================================>] 
```



### LIST

`docker service list` list all services

**list output**

```
ID             NAME      MODE         REPLICAS   IMAGE          PORTS
k5o47pf4dbuk   nginx     replicated   5/5        nginx:latest
```
service named **nginx** with **5** running containers from image **nginx:latest**

### PS

`docker service ps nginx` list all *containers* on given *service*

**ps output**

```
ID             NAME      IMAGE          NODE          DESIRED STATE   CURRENT STATE           ERROR     PORTS
ku2giyrsoz7y   nginx.1   nginx:latest   montells-T4   Running         Running 9 minutes ago             
emznxq42dzmw   nginx.2   nginx:latest   helen-T490    Running         Running 9 minutes ago             
vtez10wy18po   nginx.3   nginx:latest   montells-T4   Running         Running 9 minutes ago             
lrcg9wq35esn   nginx.4   nginx:latest   helen-T490    Running         Running 9 minutes ago             
gaou8km2vaqp   nginx.5   nginx:latest   montells-T4   Running         Running 9 minutes ago             
```

### LOGS

`docker service logs nginx` logs of a given *service*

**logs output**

```
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
nginx.4.lrcg9wq35esn@helen-T490    | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
nginx.4.lrcg9wq35esn@helen-T490    | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
nginx.2.emznxq42dzmw@helen-T490    | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
nginx.2.emznxq42dzmw@helen-T490    | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
nginx.4.lrcg9wq35esn@helen-T490    | /docker-entrypoint.sh: Configuration complete; ready for start up
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: using the "epoll" event method
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
nginx.2.emznxq42dzmw@helen-T490    | /docker-entrypoint.sh: Configuration complete; ready for start up
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: nginx/1.29.1
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14+deb12u1) 
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: using the "epoll" event method
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: OS: Linux 6.8.0-71-generic
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: nginx/1.29.1
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14+deb12u1) 
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker processes
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 29
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: OS: Linux 6.8.0-71-generic
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 30
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 31
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 32
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker processes
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 33
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 34
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 29
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 30
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 35
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 31
nginx.4.lrcg9wq35esn@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 36
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 32
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 33
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 34
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 35
nginx.2.emznxq42dzmw@helen-T490    | 2025/09/04 09:09:51 [notice] 1#1: start worker process 36
```

### RM

`docker service rm nginx` remove given service

**rm output**

```
nginx
```

### SCALE

`docker service scale nginx=8` set the number of *containers* of a given *service* to a given *number*

**scale output**

```
nginx scaled to 8
overall progress: 8 out of 8 tasks 
1/8: running   [==================================================>] 
2/8: running   [==================================================>] 
3/8: running   [==================================================>] 
4/8: running   [==================================================>] 
5/8: running   [==================================================>] 
6/8: running   [==================================================>] 
7/8: running   [==================================================>] 
8/8: running   [==================================================>] 
```

### UPDATE

`docker service update --image ubuntu/apache2 nginx` update the service. Usefull for deploying new versions naming images according commits.

**update output**

```
overall progress: 5 out of 5 tasks 
1/5: running   [==================================================>] 
2/5: running   [==================================================>] 
3/5: running   [==================================================>] 
4/5: running   [==================================================>] 
5/5: running   [==================================================>] 
verify: Service nginx converged 
```

### ROLLBACK

`docker service rollback nginx` roolback one step (latest deployment setup)

**rollback output**

```
nginx
rollback: manually requested rollback 
overall progress: rolling back update: 5 out of 5 tasks 
1/5: running   [==================================================>] 
2/5: running   [==================================================>] 
3/5: running   [==================================================>] 
4/5: running   [==================================================>] 
5/5: running   [==================================================>] 
verify: Service nginx converged 
```
