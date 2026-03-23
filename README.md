# Taller de Productividad Basada en Herramientas Tecnologicas

Aplicacion web de demostracion desarrollada para la **Universidad Tecmilenio** dentro del **Taller de Productividad Basada en Herramientas Tecnologicas**.

El proyecto muestra una base moderna de desarrollo con Spring Boot, pruebas automatizadas y soporte para flujo CI.

## Objetivo
Demostrar capacidades clave del taller:
1. **Backend con Java y Spring Boot**.
2. **Interfaz web estatica moderna**.
3. **Calidad de software con pruebas automatizadas**.
4. **Practicas de automatizacion para CI/CD**.

## Stack tecnologico
- **Lenguaje**: Java 17
- **Framework**: Spring Boot 3.2.3
- **Build tool**: Maven Wrapper (`mvnw`, `mvnw.cmd`)
- **Frontend**: HTML + CSS (archivo estatico)
- **Testing**: JUnit 5, MockMvc, Spring Boot Test

## Arquitectura
La arquitectura actual esta documentada en:
- `docs/ARCHITECTURE.md`

Incluye vista general, componentes, flujos HTTP, estrategia de pruebas, riesgos y hoja de ruta.

## Ejecucion local

### Requisitos
- Java 17+

### Compilar y probar
```powershell
.\mvnw.cmd clean test
```

### Levantar la aplicacion
```powershell
.\mvnw.cmd spring-boot:run
```

URL local:
- `http://localhost:8080/`

## Endpoints
- `GET /` - Sirve la pagina principal (`src/main/resources/static/index.html`).
- `GET /api/hello` - Endpoint REST de saludo desde `HelloController`.

## Estructura principal
```text
src/
  main/
	java/com/example/demo/
	  DemoApplication.java
	  HelloController.java
	resources/static/
	  index.html
  test/
	java/com/example/demo/
	  DemoApplicationTests.java
	  HelloControllerTest.java
	  IndexIntegrationTest.java
docs/
  ARCHITECTURE.md
CHANGELOG.md
```

## Historial de cambios
Consulta `CHANGELOG.md` para ver las versiones y cambios registrados.

---
© 2026 **Universidad Tecmilenio** | Taller de Productividad Basada en Herramientas Tecnologicas.
