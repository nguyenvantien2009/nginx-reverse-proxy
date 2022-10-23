# Nginx Proxy Docker Compose

## Build Docker Image from Dockerfile in Docker Compose

## Mount Nginx Config of proxy for easy updating

In the path [`./reverse-proxy/nginx.conf`](./reverse-proxy/nginx.conf) we define proxy directive help
passed to original server. But in the development process, we need change on a regular basis. Mount it
to local directory will a good solution for easy for using.

## Nginx Proxy Caching



## References

1. Docker Compose Nginx Reverse Proxy Multiple Containers <https://www.bogotobogo.com/DevOps/Docker/Docker-Compose-Nginx-Reverse-Proxy-Multiple-Containers.php>
2. Introduction to Docker Compose - <https://www.baeldung.com/ops/docker-compose>
