# L2 Drupal project

## Pré-requisitos

Antes de começar, você precisa ter o seguinte instalado:

- [Lando](https://lando.dev/) (versão 3.0 ou superior)
- [Docker](https://www.docker.com/) (instalação do Lando inclui o Docker)

## Rodando o projeto

Acesse a pasta do projeto

```
cd pasta-do-projeto
```

### Executando o projeto

No terminal

```
lando start
lando composer install
```

### Importando o banco inicial
Na pasta do projeto, existe um db inicial.

```
lando db-import l2-app-db.sql.gz
```

### Importando as configurações

```
lando drush cim -y
```

Com isso, o projeto ja esta rodando e com os requisitos do projeto aplicados.

```
'http://l2-app.lndo.site/'
'https://l2-app.lndo.site/'
```

## Acessando o admin

Temos dois usuários cadastrados, um admin, com todas as permissões e um com perfil de marketing, que pode editar somentes os cases.

### admin
```
user: admin
password: 9pK6NDxBvr
```

### marketing
```
user: marketing
password: 123456
```

## API de cases

A api, inicialmente, possui 2 endpoints:
1 - Retorna todos os resultados de cases
2 - Passar o id na url para retornar os dados no node.

Ambos os endpoints retornam os seguintes dados de cada node:
- nid
- title
- description
- image_formatted (imagem formatada para 480x480)
- image_original
- url_original (url do node no projeto)

### Endpoint #1
```
https://l2-app.lndo.site/api/cases
```

### Endpoint #2
```
https://l2-app.lndo.site/api/cases/{id}
```
