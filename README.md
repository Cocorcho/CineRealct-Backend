# CineReact - Backend API

API REST desarrollada con **FastAPI** y **SQLModel** para la gestión del catálogo de películas, géneros y salas del cine CineReact.

## Tecnologías utilizadas

- **Python 3.10+**
- **FastAPI**: Framework web moderno y de alto rendimiento.
- **SQLModel / SQLAlchemy**: ORM para interacción con base de datos SQLite.
- **Alembic**: Control de versiones y migraciones de base de datos.
- **Uvicorn**: Servidor ASGI de producción.
- **FastAPI-Pagination**: Paginación integrada para endpoints.

## Requisitos previos

- Python 3.10 o superior instalado.

## Instalación y configuración

1. **Crear y activar el entorno virtual:**
   ```bash
   python -m venv venv
   # En Windows PowerShell:
   .\venv\Scripts\Activate.ps1
   # En Linux / macOS:
   source venv/bin/activate
   ```

2. **Instalar dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Variables de entorno (opcional):**
   Copiar `.env.example` a `.env`:
   ```bash
   cp .env.example .env
   ```

4. **Ejecutar migraciones de base de datos:**
   ```bash
   alembic upgrade head
   ```

5. **Poblar la base de datos con datos iniciales (Seed):**
   ```bash
   python seed.py
   ```

## Ejecución del servidor

Para iniciar el servidor en modo desarrollo con recarga automática:

```bash
uvicorn src.main:app --reload
```

El servidor estará disponible en `http://localhost:8000`.

## Documentación interactiva

- **Swagger UI:** `http://localhost:8000/docs`
- **ReDoc:** `http://localhost:8000/redoc`

## Endpoints principales

- **Películas:**
  - `GET /peliculas/`: Listar películas (con paginación).
  - `GET /peliculas/{id}`: Obtener detalle de una película.
  - `POST /peliculas/`: Crear una película.
  - `PUT /peliculas/{id}`: Actualizar película.
  - `DELETE /peliculas/{id}`: Eliminar película (soporta borrado lógico con `?logico=true`).
- **Géneros:**
  - `GET /generos/`: Listar géneros (con paginación).
  - `GET /generos/{id}`: Obtener detalle de un género.
  - `POST /generos/`: Crear un género.
  - `PUT /generos/{id}`: Actualizar género.
  - `DELETE /generos/{id}`: Eliminar género.
- **Salas:**
  - `GET /salas/`: Listar salas (con paginación).
  - `GET /salas/{id}`: Obtener detalle de una sala.
  - `POST /salas/`: Crear una sala.
  - `PUT /salas/{id}`: Actualizar sala.
  - `DELETE /salas/{id}`: Eliminar sala.
