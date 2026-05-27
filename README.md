# Backend Despacho

API REST desarrollada con Spring Boot para el sistema de despacho de Innovatech Chile.

## Tecnologías
- Java 17
- Spring Boot 3.4.4
- MySQL 8.0
- Docker (multi-stage build)

## Requisitos
- Docker Desktop instalado
- MySQL 8.0

## Variables de entorno
| Variable | Descripción | Ejemplo |
|---|---|---|
| DB_ENDPOINT | Host de la base de datos | localhost |
| DB_PORT | Puerto MySQL | 3306 |
| DB_NAME | Nombre de la BD | db_despacho |
| DB_USERNAME | Usuario MySQL | root |
| DB_PASSWORD | Contraseña MySQL | root1234 |

## Cómo ejecutar con Docker
`ash
docker build -t backend-despacho ./Springboot-API-REST-DESPACHO
docker run -p 8081:8081 \
  -e DB_ENDPOINT=localhost \
  -e DB_PORT=3306 \
  -e DB_NAME=db_despacho \
  -e DB_USERNAME=root \
  -e DB_PASSWORD=root1234 \
  backend-despacho
`

## Documentación API
Swagger UI disponible en: http://localhost:8081/swagger-ui.html

## Pipeline CI/CD
El pipeline se activa con cada push a la rama deploy:
1. Construye la imagen Docker
2. Publica en Docker Hub
3. Despliega en EC2

## Estructura
- Springboot-API-REST-DESPACHO/ - Código fuente
- Dockerfile - Configuración Docker multi-stage
- .github/workflows/deploy.yml - Pipeline CI/CD
