FROM nginx:latest

#diretorio de trabalho
WORKDIR /app

#rodando os comandos
RUN apt-get update && \
    apt-get install vim -y

#copiando os arquivos para dentro da imagem 
COPY /html /usr/share/nginx/html