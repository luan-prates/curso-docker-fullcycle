# curso-docker-fullcycle
curso de docker do programa desenvolvedor fullcycle

## comandos

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

