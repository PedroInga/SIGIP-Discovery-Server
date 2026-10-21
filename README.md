# SIGIP-Discovery-Server

Servidor Eureka: registro y descubrimiento de servicios.

## Funcionalidad

- Panel: http://localhost:8761
- Cada servicio se registra con un `instance-id` aleatorio, así se pueden levantar varias instancias del mismo servicio.
- En la nube (perfil `cloud`) no se usa: los servicios se ubican por variables de entorno.

## Ejecución

Puerto `8761`.

## Repositorio

Este repositorio es uno de los 12 de SIGIP (un repositorio por microservicio). Es un proyecto Maven
independiente: no depende de ningún POM padre ni de otro repositorio.

## Compilar y ejecutar

Requisitos: Java 25 (Maven no hace falta, el repo trae `mvnw`).

```powershell
.\mvnw.cmd clean verify          # compila y ejecuta las pruebas
.\mvnw.cmd spring-boot:run       # arranca en el puerto 8761
```

En Linux/macOS usa `./mvnw` en lugar de `.\mvnw.cmd`.

## Docker

```powershell
docker build -t sigip/discovery-server .
```

Para levantar todo SIGIP junto (los 12 repos, MySQL y RabbitMQ) usa el `docker-compose.yml` de la carpeta
`SIGIP` que contiene a los 12 repositorios.
