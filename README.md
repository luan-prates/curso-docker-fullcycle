# curso-docker-fullcycle
curso de docker do programa desenvolvedor fullcycle

## iniciando

Hello World
``` docker run hello-world```

### Execurando Ububtu
lista os containes 
``` docker ps ```

lista os containes inclusive os que não estão rodando
``` docker ps -a```

Roda um container ubuntu com o bash aberto em modo interativo.
``` docker run -it ubuntu bash```

inicia um container 
``` docker start nome_do_container```

para um container 
``` docker stop nome_do_container```


Roda um container ubuntu com o bash aberto em modo interativo e já remove o container.
``` docker run -it --rm ubuntu bash```

### Publicando portas com nginx

Rodando nginx
``` docker run nginx```

Rodando nginx e mapeando para a porta 8080.
``` docker run -p 8080:80 nginx```

Rodando nginx e mapeando para a porta 8080 em "segundo plano".
``` docker run -d -p 8080:80 nginx```

### Removendo containers

Remove um container
``` docker rm id_do_container ou nome_do_container```

Força a remoção do container
``` docker rm id_do_container ou nome_do_container -f```

### Arquivos em um container

Rodando o nginx na porta 8080 em "segundo plano" com o nome de meu_nginx.
``` docker run -d --name meu_nginx -p 8080:80 nginx```

Executando um comando dentro do container rodando.
```docker exec meu_nginx ls```

Executando o bash dentro do container rodando.
```docker exec -it meu_nginx bash```

### Mapeando volumes
o comando -v cria a pasta se ela não existir
```docker run -d --name meu_nginx -p 8080:80 -v $(pwd)/nginx/html/:/usr/share/nginx/html nginx```

#### bind mount
o comando mount é mais recente mas não cria a pasta se ela não existir
```docker run -d --name o_nginx -p 8088:80 --mount type=bind,source="$(pwd)/nginx/html/",target=/usr/share/nginx/html nginx```

#### volumes
vamos ver quais comandos são possiveis com o comando volume
```docker volume```

lista os volumes
```docker volume ls```

criando um volume
```docker volume create meu_volume```

especionado um volume

``` docker volume inspect nome_volume```

montando um volume já existente 
``` docker run --name nginx_volume -d -p 8888:80 --mount type=volume,source=meu_volume,target=/app nginx```

entrando na maquina 
``` docker exec -it nginx_volume bash```

limpando os volumes 
``` docker volume prune```

## imagens

baixando imagens 
```docker pull ubuntu```

