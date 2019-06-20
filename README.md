# Dockerised Jolokia Proxy

[Dockerfile](https://github.com/alvarolmedo/docker-jolokia-proxy)

Run standalone:

```sh
docker run -d --name jolokia -p 8080:8080 alvarolmedo/jolokia-proxy
```

Kubernetes container snippet (add to Telegraf or a standalone deployment):

```yml
containers:
- name: jolokia
  image: alvarolmedo/jolokia-proxy
  ports:
  - containerPort: 8080
  resources:
    requests:
      memory: 128Mi
      cpu: 0.1
    limits:
      memory: 1Gi
      cpu: 0.5
```
