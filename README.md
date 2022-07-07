# Docker

## Comandos

```sh
$ docker ps
# -a lista todos os containers
# -q lista somente os ids do containers

$ docker run hello-world
$ docker run -it ubuntu bash
# -i interativo
# -t terminal (tty)
# --rm auto-remove
# --name NOME define o nome do container
# -d (detach) executa e não aclopa o serviço no terminal
# -p 8080:80 redirecionamento de porta

$ docker run -d --name nginx -p 8080:80 nginx

$ docker rm $(docker ps -aq) -f
$ docker rm d79bf4a65267
# -f força a remoção do container

$ docker start nginx
$ docker stop nginx

$ docker exec -it nginx bash

$ docker run -d --name nginx -p 8080:80 -v ${pwd}/html:/usr/share/nginx/html
$ docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)"/html,target=/usr/share/nginx/html
# -v bind do volumr, mas ele cria o diretório caso não exista
# --mount type=bind faz o bind do volume e não cria o diretório caso não existe. retorna um erro

$ docker volume ls
$ docker volume create meuvolume
$ docker run -d --name nginx -p 8080:80 --mount type=volume,source=meuvolume,target=/app
```
