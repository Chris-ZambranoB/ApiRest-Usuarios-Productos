# FastAPI REST API - Usuarios y Productos 

API RESTful desarrollada con **FastAPI** que implementa autenticación segura JWT, persistencia de datos relacional y gestión de usuarios con sus respectivos productos asociados.

---

## Tecnologías Utilizadas

* **Framework:** FastAPI
* **Base de Datos:** SQLite (SQLAlchemy ORM)
* **Autenticación & Seguridad:** JWT (JSON Web Tokens), Bcrypt (Hashing de contraseñas), `python-dotenv`
* **Validación de Datos:** Pydantic (v2)
* **Servidor ASGI:** Uvicorn

---

## Características Principales

*  **Seguridad Avanzada:** Encriptación de contraseñas con `bcrypt` (limitado a 72 bytes de forma segura) y expiración de tokens JWT en 30 minutos.
*  **Rutas Protegidas:** Middlewares de autenticación mediante esquema `HTTPBearer` para verificar tokens en endpoints privados.
*  **Relaciones ORM:** Relación 1:N entre la tabla `usuarios` y `productos` (Un usuario posee múltiples productos registrados).
*  **CORS Habilitado:** Middleware configurado para permitir peticiones cross-origin.

---

##  Instalación y Configuración Local

### 1. Clonar el repositorio
```bash
git clone [https://github.com/Chris-ZambranoB/ApiRest-Usuarios-Productos.git](https://github.com/Chris-ZambranoB/ApiRest-Usuarios-Productos.git)
cd ApiRest-Usuarios-Productos
```

### 2. Crear y activar un entorno virtual

En Windows (CMD / PowerShell):
```bash
python -m venv .venv
.venv\Scripts\activate
```

En Linux / macOS:
```bash
python3 -m venv .venv
source .venv/bin/activate
```
### 3. Instalar las dependencias

Con el entorno virtual activado, instala todas las librerías indicadas en el requirements.txt:
```bash
pip install -r requirements.txt
```
### 4. Configurar variables de entorno

Crea un archivo llamado .env en la raíz del proyecto y define las variables de configuración de tu aplicación (por ejemplo, para JWT):
```bash
SECRET_KEY=tu_clave_secreta_aqui
```
### 5. Ejecutar la aplicación

Inicia el servidor de desarrollo utilizando Uvicorn:
```bash
uvicorn main:app --reload
```
La API estará ejecutándose en http://127.0.0.1:8000.

### Documentación Interactiva

Una vez que el servidor esté en marcha, puedes probar todos los endpoints desde la documentación interactiva:

Swagger UI: http://127.0.0.1:8000/docs

ReDoc: http://127.0.0.1:8000/redoc
