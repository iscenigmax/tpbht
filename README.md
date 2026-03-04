# Demo Web App CI/CD

Esta es una aplicación web de demostración creada en Java con **Spring Boot**. El propósito de este proyecto es demostrar:
1. Creación de una API REST básica.
2. Implementación de **Pruebas Unitarias** con JUnit 5 y `MockMvc`.
3. Configuración de **Integración Continua (CI)** mediante **GitHub Actions**.
4. Buenas prácticas de administración de proyecto utilizando la plataforma Git.

## Requisitos
- Java 17 o superior
- Maven 3.6+ (o usa el wrapper incluido `mvnw`)

## Compilar y Ejecutar Pruebas
Para compilar el proyecto y correr las pruebas unitarias localmente, ejecuta en la raíz del proyecto:

En Windows:
```cmd
mvnw.cmd clean test
```

En Linux/Mac:
```bash
./mvnw clean test
```

## Ejecutar la Aplicación
Para levantar el servidor de desarrollo en tu máquina local:

```cmd
mvnw.cmd spring-boot:run
```
La aplicación estará disponible en [http://localhost:8080/](http://localhost:8080/).

## Integración Continua (CI)
Este proyecto cuenta con un workflow de GitHub Actions (`.github/workflows/ci.yml`).
Sirve de la siguiente forma:
- Cada cambio enviado (`push`) a las ramas principales (`main`, `master`) disparará un proceso.
- Cada _Pull Request_ abrirá una validación para asegurar que el código compila y las pruebas pasan exitosamente antes de permitir la unión del código.
Así se asegura que el proyecto mantenga su integridad.

## Administración de Proyecto
Para gestionar correctamente este proyecto en GitHub, se recomienda:
- **Issues**: Reporta bugs y describe nuevas características antes de escribir código.
- **Branches (Ramas)**: Usa una rama separada para cada Issue (ej. `feature/1-hello-world`).
- **Pull Requests (PR)**: Somete el código de tu rama usando un PR para que CI lo valide y otro desarrollador lo revise.
- **Releases**: Usa los tags de Git (e.g. `v1.0.0`) y las Releases de GitHub para marcar versiones estables del código.
