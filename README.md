## k8s-registry-proxy-cache - k8s镜像源代理缓存 

multi registries proxy for k8s to cache images


### usages

#### server
edit .env file to set the HTTPS_PROXY


docker-compose up -d


#### client
edit system hosts file


add hosts
```
server_ip gcr.io
server_ip k8s.gcr.io
server_ip quay.io
```


add /etc/docker/daemon.json
```
{
  "insecure-registries": ["http://gcr.io", "http://k8s.gcr.io", "http://quay.io"]
}
```

restart docker service
