# Instalación

## Clonar repositorio
```bash
git clone https://github.com/usuario/repositorio.git
cd repositorio
```

## Instalar dependencias
### Backend
```bash
./mvnw clean install
```

### Frontend
```bash
npm install
```

## Configurar variables de entorno
```env
APP_PORT=8080
DB_HOST=localhost
DB_PORT=5432
DB_NAME=nombre_bd
DB_USER=usuario
DB_PASSWORD=password
```

## Ejecutar en desarrollo
### Backend
```bash
./mvnw spring-boot:run
```

### Frontend
```bash
npm run dev
```

## Pruebas manuales
1. Levantar la aplicación
2. Acceder desde el navegador
3. Validar operaciones básicas
4. Revisar logs y respuesta del sistema
