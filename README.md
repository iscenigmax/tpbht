# Taller de Productividad Basada en Herramientas Tecnológicas (1)

Este proyecto es una aplicación web de demostración desarrollada para la **Universidad Tecmilenio** como parte del **Taller de Productividad Basada en Herramientas Tecnológicas**. El objetivo es demostrar la implementación de un ecosistema de desarrollo moderno, eficiente y automatizado.

## 🚀 Propósito del Proyecto
Demostrar las competencias adquiridas en el taller, incluyendo:
1. **Desarrollo Backend**: Creación de una arquitectura robusta con Java 17 y Spring Boot 3.2.3.
2. **Interfaz Moderna**: Implementación de una UI Premium con estética Glassmorphic.
3. **Calidad de Software**: Pruebas unitarias automatizadas con JUnit 5 y MockMvc.
4. **DevOps & CI/CD**: Automatización total mediante GitHub Actions.

## 🛠️ Stack Tecnológico
- **Lenguaje**: Java 17
- **Framework**: Spring Boot 3.2.3
- **Gestor de Dependencias**: Maven
- **Estilo**: Vanilla CSS (Glassmorphism)
- **CI/CD**: GitHub Actions

## 💻 Ejecución Local

### Requisitos
- Java 17 o superior.
- Maven 3.6+ (o el wrapper `mvnw` incluido).

### Compilar y Probar
Para asegurar la integridad del código, ejecuta:
```cmd
.\mvnw.cmd clean test
```

### Levantar la Aplicación
Para iniciar el servidor de desarrollo:
```cmd
.\mvnw.cmd spring-boot:run
```
La aplicación estará disponible en [http://localhost:8080/](http://localhost:8080/).

## 🔗 Endpoints del API
- `GET /`: Interfaz visual principal (HTML Estático).
- `GET /api/hello`: Endpoint REST de prueba.

---
© 2024 **Universidad Tecmilenio** | Taller de Productividad Basada en Herramientas Tecnológicas.
