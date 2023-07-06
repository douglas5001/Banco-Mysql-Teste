<h1>Configuração do Mysql no Ambiente Linux, utilizando</h1>

Docker-Compose
```
version: '3'
services:
  mysql:
    image: mysql:8.0.29-debian
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    volumes:
      - /home/Bancos/Mysql:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: Bola@2020
      MYSQL_DATABASE: db_mysql
    networks:
      - net_principal
    ports:
      - 30000:3306

volumes:
  MYSQL_VOLUME:
    driver: local
    driver_opts:
      type: none
      o: bind
      device: /home/Bancos/Mysql
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

Comando Basicos

listar bancos
```
SHOW DATABASES;
```
Listar Tabelas
```
SHOW TABLES;
```

```
ddddd
```

```
ddddd
```

```
ddddd
```
