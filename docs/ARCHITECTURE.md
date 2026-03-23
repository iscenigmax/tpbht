# Arquitectura de la Aplicacion

## 1. Objetivo y Alcance
Este documento describe la arquitectura actual de la aplicacion `demo`, una solucion Spring Boot orientada a:
- Exponer un endpoint REST de prueba.
- Servir una interfaz web estatica desde el mismo backend.
- Validar funcionamiento con pruebas unitarias e integracion.

Alcance actual:
- Monolito ligero (una sola aplicacion Java).
- Sin base de datos ni integraciones externas.
- Despliegue como JAR ejecutable de Spring Boot.

## 2. Vista General (Contenedores)
La arquitectura es de una sola aplicacion con dos superficies HTTP:

```text
[Cliente Web / Navegador]
          |
          | HTTP
          v
[Spring Boot App]
  - REST API: /api/hello
  - Static Content: /
```

Componentes principales:
- Bootstrap de aplicacion: `src/main/java/com/example/demo/DemoApplication.java`.
- Controlador REST: `src/main/java/com/example/demo/HelloController.java`.
- UI estatica (HTML/CSS): `src/main/resources/static/index.html`.

## 3. Flujo de Solicitudes
### 3.1 Flujo REST (`GET /api/hello`)
1. El cliente envia `GET /api/hello`.
2. Spring MVC enruta al metodo `hello()` en `HelloController`.
3. El controlador retorna una cadena de texto.
4. Spring serializa y responde `200 OK` con `text/plain`.

### 3.2 Flujo de Pagina Principal (`GET /`)
1. El cliente envia `GET /`.
2. Spring Boot detecta y sirve `static/index.html` como welcome page.
3. El navegador renderiza HTML + CSS embebido.

## 4. Capas y Responsabilidades
Aunque hoy es una app simple, se mantiene una separacion basica:
- Capa de entrada web (Controller): recibe solicitudes y define rutas.
- Capa de presentacion estatica (Static): pagina principal y estilos.
- Configuracion/arranque (Application): inicializacion de Spring Boot.

No existe aun capa de servicio o repositorio; seria la siguiente evolucion natural si crece la logica de negocio.

## 5. Dependencias Tecnologicas
Definidas en `pom.xml`:
- `spring-boot-starter-web`: servidor embebido, Spring MVC y API REST.
- `spring-boot-starter-test` (scope test): JUnit 5, Spring Test, MockMvc, AssertJ.

Versiones clave:
- Java 17
- Spring Boot 3.2.3
- Maven Wrapper (`mvnw` / `mvnw.cmd`)

## 6. Estrategia de Pruebas
Pruebas incluidas:
- `src/test/java/com/example/demo/DemoApplicationTests.java`
  - Verifica carga de contexto Spring (`@SpringBootTest`).
- `src/test/java/com/example/demo/HelloControllerTest.java`
  - Prueba web por slice (`@WebMvcTest`) para `GET /api/hello`.
- `src/test/java/com/example/demo/IndexIntegrationTest.java`
  - Integracion con servidor real en puerto aleatorio para `GET /`.

Cobertura funcional actual:
- Disponibilidad del endpoint REST.
- Contenido esperado en la respuesta REST.
- Disponibilidad de la pagina principal estatica.
- Presencia de textos clave de la UI.

## 7. Operacion y Despliegue
Ejecucion local:
- Construccion y pruebas: `./mvnw.cmd clean test` (Windows).
- Arranque: `./mvnw.cmd spring-boot:run`.

Empaquetado:
- Artefacto principal: `target/demo-0.0.1-SNAPSHOT.jar`.

## 8. Decisiones Arquitectonicas
1. **Monolito simple primero**: reduce complejidad para un entorno de taller/demo.
2. **Backend + Frontend estatico en el mismo proceso**: menos piezas operativas.
3. **Pruebas por capas (slice + integracion)**: equilibrio entre rapidez y confianza.

## 9. Riesgos y Limites Actuales
- Sin persistencia de datos ni capa de negocio formal.
- Sin observabilidad avanzada (metricas, tracing, dashboards).
- Sin autenticacion/autorizacion.
- `index.html` con estilos embebidos; mantenibilidad limitada al crecer UI.

## 10. Hoja de Ruta Recomendada
1. Introducir capa `service` para separar logica de negocio del controlador.
2. Extraer estilos/JS de `index.html` a archivos dedicados en `static/`.
3. Agregar `@ControllerAdvice` para manejo uniforme de errores.
4. Incorporar Actuator para salud y metricas operativas.
5. Definir perfilado por ambientes (`dev`, `test`, `prod`) en configuracion.

---
Este documento describe el estado actual del repositorio en marzo de 2026 y sirve como base para evolucionar a una arquitectura multicapa cuando el dominio crezca.

