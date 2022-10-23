# Nginx Proxy Docker Compose

## Build Docker Image from Dockerfile in Docker Compose

## Mount Nginx Config of proxy for easy updating

In the path [`./reverse-proxy/nginx.conf`](./reverse-proxy/nginx.conf) we define proxy directive help
passed to original server. But in the development process, we need change on a regular basis. Mount it
to local directory will a good solution for easy for using.

## Nginx Proxy Caching

For any reason, we need cache between original server to reverse proxy. Nginx support config cache with
expire time, limit size of cache...

```code
// ...
proxy_cache_path   /data/nginx/cache keys_zone=mycache:10m max_size=200m;
// ...
server {
    listen 8080;
    proxy_cache mycache;

    location / {
        proxy_pass http://docker-nginx;
        proxy_cache_valid 200 1d;
        proxy_redirect off;
    }
}
// ...
```

## References

1. Docker Compose Nginx Reverse Proxy Multiple Containers <https://www.bogotobogo.com/DevOps/Docker/Docker-Compose-Nginx-Reverse-Proxy-Multiple-Containers.php>
2. Introduction to Docker Compose - <https://www.baeldung.com/ops/docker-compose>
