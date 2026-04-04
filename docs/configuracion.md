# Configuración

## Archivos principales
- `.env`
- `application.properties`
- `application.yml`
- `docker-compose.yml`

## Ejemplo de configuración
```properties
server.port=8080
spring.datasource.url=jdbc:postgresql://localhost:5432/nombre_bd
spring.datasource.username=usuario
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
```

## Requisitos previos
- Base de datos creada
- Variables de entorno definidas
- Credenciales válidas
- Puertos disponibles
