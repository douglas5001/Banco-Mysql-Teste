<h1>Configuração do Mysql no ambiente linux, utilizando Docker-Compose</h1>

<h3>Renomeie o repositorio e coloque na pasta onde ficara amarzenado os dados do banco</h3>
<hr>
Instalação do Mysql no docker

Docker-Compose
```
version: '3'
services:
  mysql:
    image: mysql:8.0.29-debian
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    volumes:
      - /repositorio/local/do/arquivo:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: Sua@Senha
      MYSQL_DATABASE: db_mysql
    networks:
      - net_principal
    ports:
      - 30000:3306

networks:
  net_principal:

volumes:
  MYSQL_VOLUME:
    driver: local
    driver_opts:
      type: none
      o: bind
      device: /repositorio/local/do/arquivo
```
Para executar o arquivo

```
docker compose up -d
```
Agora acesso o container com o comando abaixo
```
docker exec -t Nome-Container-Docker /bin/bash
```
Acesse o Mysql
```
mysql -uUSER-DE-ACESSO -p
```
<br>
<hr>

<h2>Criar database</h2>

```
CREATE DATABASE NOME-DO-BANCO;
```
<br>
<h2>Criar tabela</h2>

```
 CREATE TABLE NOME-DA-TABELA;
```
<br>
<hr>
<h3>Comandos de busca</h3>
listar bancos

```
SHOW DATABASES;
```
Listar Tabelas
```
SHOW TABLES;
```
Retornar tabela
```
SELECT * FROM nome-DA-tabela;
```

