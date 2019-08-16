<img src="http://drnavia.com/logos/POC-GraphQL-2019.png"></img>

## Base de Datos MongoDB - [Dokerizada]
![Branch stable](https://img.shields.io/badge/branch-master-blue.svg)
![version](https://img.shields.io/badge/mongodb-v4.x-499D4A.svg)
![version](https://img.shields.io/badge/docker%20compose-build-309CEC.svg)<br>
Despliegue la Base de datos (MongoDB) necesaria para conectarla a la API RESTful y a la API GraphQL. La Base de Datos permite almacenar la información del **listado de Países con Estados y Localidades**.<br>

## Pre-requisitos
Debes tener instalado:
+ Git
+ Docker
+ Docker Compose

## Despliegar la Base de Datos
1. Clonar el repo:
```bash
git clone https://github.com/drnavia/poc-gql-mongodb.git
```
2. Construir la imagen del contenedor con Docker Compose:
```bash
docker-compose -f dc-gql-mongodb.yml build
```
3. Levantar el contenedor de la API:
```bash
docker-compose -f dc-gql-mongodb.yml up -d
```
4. El siguiente comando se utiliza para conectarse a la base:
```bash
mongodb://poc-gql-mongodb:27017/poc-graphql-db
```

## Carga inicial
1. Conectarse al contenedor de la base:
```bash
docker exec -it poc-gql-mongodb bash
```
2. Posicionarse en la carpeta "carga-inicial":
```bash
cd data/db/carga-inicial
```
3. Ejecutar el comando para importar los datos a la base:
```bash
mongoimport --db poc-graphql-db --collection paises --file paises.json
```
4. Salir del contenedor de la base:
```bash
exit
```

<br><br>
**[ DrN ]**