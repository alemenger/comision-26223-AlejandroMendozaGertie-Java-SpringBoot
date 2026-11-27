# Articulo API MySQL

**Alumno:** Alejandro Mendoza Gertie  
**Comisión:** 26223

## Descripción del proyecto
API REST para la gestión de artículos (id, nombre y precio), con arquitectura monolítica en capas
(Controller → Service → ServiceImpl → Repository → MySQL). Permite registrar, listar, consultar,
modificar y eliminar artículos, y guarda los datos de forma persistente en MySQL.

## Tecnologías utilizadas
- Java 17
- Spring Boot 3.2.5
- Maven
- Spring Web
- Spring Data JPA / Hibernate
- MySQL
- Postman (pruebas)
- Visual Studio Code

## Requisitos para ejecutar la aplicación
- JDK 17 instalado
- Maven (o el soporte de Maven de VS Code)
- MySQL en funcionamiento (XAMPP o instalación propia)
- Postman

## Configuración de MySQL
1. Iniciar el servidor MySQL.
2. Crear la base de datos:
   ```sql
   CREATE DATABASE articulos_db;
   ```
3. Revisar `src/main/resources/application.properties` y ajustar el **puerto**, el **usuario** y la
   **contraseña** según tu instalación (por defecto MySQL usa el puerto 3306; en este proyecto se usó 3307).
4. La tabla `articulo` la crea Hibernate automáticamente al iniciar la aplicación.

## Instrucciones de ejecución
1. Clonar el repositorio.
2. Abrir la carpeta en Visual Studio Code.
3. Ejecutar la clase `ArticuloApiApplication` (botón **Run**) o, desde la terminal: `mvn spring-boot:run`.
4. La API queda disponible en `http://localhost:8080/api/articulos`.

## Endpoints disponibles
| Método | Endpoint | Descripción | Respuestas |
|--------|----------|-------------|------------|
| GET | `/api/articulos` | Lista todos los artículos | 200 |
| GET | `/api/articulos/{id}` | Consulta un artículo por id | 200 / 404 |
| POST | `/api/articulos` | Crea un artículo | 200 |
| PUT | `/api/articulos/{id}` | Modifica un artículo | 200 / 404 |
| DELETE | `/api/articulos/{id}` | Elimina un artículo | 204 / 404 |

Ejemplo de cuerpo para POST y PUT:
```json
{ "nombre": "Teclado", "precio": 15000 }
```

## Pruebas
La colección de Postman `Articulo_API_MySQL.postman_collection.json` está incluida en este repositorio.

## Video de presentación
PEGAR AQUÍ EL LINK DE YOUTUBE
