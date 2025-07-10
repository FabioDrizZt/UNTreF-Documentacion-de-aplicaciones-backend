![Banner Peliculas](https://cdn.pixabay.com/photo/2015/09/21/14/47/banner-949944_1280.jpg)

# 🎬 API de Películas con Mongoose y Express

Una **API REST** moderna para gestionar una base de datos de películas utilizando **Node.js**, **Express** y **MongoDB** con **Mongoose**.

---

## 📋 Tabla de Contenidos

- [🎬 API de Películas con Mongoose y Express](#-api-de-películas-con-mongoose-y-express)
  - [📋 Tabla de Contenidos](#-tabla-de-contenidos)
  - [✨ Características](#-características)
  - [🚀 Instalación](#-instalación)
    - [1. Clonar el repositorio](#1-clonar-el-repositorio)
    - [2. Instalar dependencias](#2-instalar-dependencias)
    - [3. Configurar variables de entorno](#3-configurar-variables-de-entorno)
    - [4. Iniciar la aplicación](#4-iniciar-la-aplicación)
  - [⚙️ Configuración](#️-configuración)
    - [Opciones de conexión recomendadas:](#opciones-de-conexión-recomendadas)
  - [🏗️ Arquitectura del Proyecto](#️-arquitectura-del-proyecto)
    - [📊 Diagrama de Arquitectura](#-diagrama-de-arquitectura)
  - [📡 Endpoints de la API](#-endpoints-de-la-api)
    - [🎯 Operaciones CRUD Básicas](#-operaciones-crud-básicas)
    - [🔍 Endpoints de Filtrado](#-endpoints-de-filtrado)
    - [📊 Códigos de Respuesta HTTP](#-códigos-de-respuesta-http)
  - [📊 Modelo de Datos](#-modelo-de-datos)
    - [Ejemplo de película válida:](#ejemplo-de-película-válida)
  - [🧪 Pruebas con API HTTP](#-pruebas-con-api-http)
    - [➕ Crear una nueva película](#-crear-una-nueva-película)
    - [✏️ Actualizar una película existente](#️-actualizar-una-película-existente)
    - [🗑️ Eliminar una película](#️-eliminar-una-película)
  - [🔧 Scripts Disponibles](#-scripts-disponibles)
  - [📝 Lista de Tareas del Proyecto](#-lista-de-tareas-del-proyecto)
    - [🚀 Funcionalidades Básicas](#-funcionalidades-básicas)
    - [🔍 Mejoras Pendientes](#-mejoras-pendientes)
    - [🛡️ Seguridad y Producción](#️-seguridad-y-producción)
    - [📊 Funcionalidades Avanzadas](#-funcionalidades-avanzadas)
    - [🧪 Testing y Calidad](#-testing-y-calidad)
  - [⚡ Tecnologías](#-tecnologías)
    - [Backend](#backend)
    - [Base de Datos](#base-de-datos)
    - [Herramientas de Desarrollo](#herramientas-de-desarrollo)
    - [Dependencias principales](#dependencias-principales)
  - [📝 Notas Importantes](#-notas-importantes)
    - [Controladores](#controladores)
    - [Middleware](#middleware)
    - [Estructura de respuestas](#estructura-de-respuestas)
  - [🤝 Contribución](#-contribución)
    - [🎬 ¡Disfruta gestionando tu colección de películas! 🍿](#-disfruta-gestionando-tu-colección-de-películas-)

---

## ✨ Características

> [!NOTE]  
> Esta API implementa un patrón **MVC** (Modelo-Vista-Controlador) para una mejor organización del código.

- ✅ **CRUD Completo** para gestión de películas
- 🔍 **Filtrado avanzado** por género, director y puntuación
- 🗃️ **Base de datos MongoDB** con Mongoose ODM
- 🏗️ **Arquitectura MVC** bien estructurada
- 🚀 **Hot reload** en desarrollo
- 📡 **RESTful API** siguiendo mejores prácticas
- 🔧 **Validación** de datos con Mongoose schemas

---

## 🚀 Instalación

> [!IMPORTANT]  
> Asegúrate de tener **Node.js** (versión 18 o superior) y **MongoDB** instalados en tu sistema.

<details>
<summary><strong>📝 Pasos de instalación detallados</strong></summary>

### 1. Clonar el repositorio
```bash
git clone <url-del-repositorio>
cd "24 - Arquitectura-con-Mongoose-y-Express"
```

### 2. Instalar dependencias
```bash
# Usando pnpm (recomendado)
pnpm install

# O usando npm
npm install
```

### 3. Configurar variables de entorno
Crea un archivo `.env` en la raíz del proyecto:
```env
DB_PROTOCOL=mongodb
DB_HOST=localhost:27017
DB_USER=tu_usuario
DB_PASS=tu_contraseña
DB_NAME=movies_db
DB_OPTIONS=retryWrites=true&w=majority
```

### 4. Iniciar la aplicación
```bash
# Modo desarrollo (con hot reload)
pnpm dev

# Modo producción
pnpm start
```

</details>

---

## ⚙️ Configuración

> [!WARNING]  
> **No olvides configurar las variables de entorno** antes de ejecutar la aplicación.

La aplicación se ejecuta por defecto en el puerto **3000**. Puedes acceder a ella en:
```
http://localhost:3000
```

<details>
<summary><strong>🔧 Configuración de MongoDB</strong></summary>

La conexión a MongoDB se configura a través de variables de entorno en el archivo `config/database.js`:

```javascript
const MONGODB_URI = `${DB_PROTOCOL}://${DB_USER}:${DB_PASS}@${DB_HOST}/${DB_NAME}?${DB_OPTIONS}`;
```

### Opciones de conexión recomendadas:
- **Local:** `mongodb://localhost:27017/movies_db`
- **MongoDB Atlas:** Usar la cadena de conexión proporcionada por Atlas
- **Docker:** `mongodb://mongodb:27017/movies_db`

</details>

---

## 🏗️ Arquitectura del Proyecto

```
24 - Arquitectura-con-Mongoose-y-Express/
├── 📄 app.js                    # Punto de entrada principal
├── 📄 api.http                  # Pruebas HTTP
├── ⚙️  config/
│   └── 📄 database.js           # Configuración de MongoDB
├── 🎮 controllers/
│   ├── 📄 movies.js             # Controladores síncronos
│   └── 📄 moviesPromesas.js     # Controladores con promesas
├── 📊 data/
│   └── 📄 movies.json           # Datos de ejemplo
├── 🏗️ models/
│   └── 📄 movie.js              # Modelo de Mongoose
├── 🛣️ routes/
│   └── 📄 movies.js             # Definición de rutas
├── 📋 package.json              # Dependencias y scripts
└── 📚 readme.md                 # Documentación
```

> [!TIP]  
> La estructura sigue el patrón **MVC** para mantener el código organizado y escalable.

### 📊 Diagrama de Arquitectura

```mermaid
graph TD
    A["👤 Cliente<br/>(Postman, Browser)"] --> B["🌐 Express Server<br/>Port 3000"]
    
    B --> C["🛣️ Router<br/>routes/movies.js"]
    
    C --> D["🎮 Controller<br/>controllers/moviesPromesas.js"]
    
    D --> E["🏗️ Model<br/>models/movie.js<br/>(Mongoose Schema)"]
    
    E --> F["🗃️ MongoDB<br/>Database"]
    
    F --> E
    E --> D
    D --> C
    C --> B
    B --> A
    
    G["⚙️ Database Config<br/>config/database.js"] --> E
    
    H["📊 Data Seed<br/>data/movies.json"] -.-> F
    
    subgraph "🔄 Operaciones CRUD"
        I["📖 GET /peliculas<br/>Obtener todas"]
        J["🔍 GET /peliculas/:id<br/>Obtener por ID"]
        K["➕ POST /peliculas<br/>Crear nueva"]
        L["✏️ PATCH /peliculas/:id<br/>Actualizar"]
        M["🗑️ DELETE /peliculas/:id<br/>Eliminar"]
    end
    
    C --> I
    C --> J
    C --> K
    C --> L
    C --> M
    
    subgraph "🔍 Filtros Avanzados"
        N["🎭 GET /peliculas?genero=:genre<br/>Por género"]
        O["🎬 GET /peliculas/director/:director<br/>Por director"]
        P["⭐ GET /peliculas/rate/:rate<br/>Por puntuación"]
    end
    
    C --> N
    C --> O
    C --> P
```

> [!NOTE]  
> Este diagrama muestra el flujo completo de datos desde el cliente hasta la base de datos, pasando por todas las capas de la arquitectura MVC.

---

## 📡 Endpoints de la API

### 🎯 Operaciones CRUD Básicas

| Método | Endpoint | Descripción | Ejemplo |
|--------|----------|-------------|---------|
| `GET` | `/` | Página principal | `http://localhost:3000/` |
| `GET` | `/peliculas` | Obtener todas las películas | `http://localhost:3000/peliculas` |
| `GET` | `/peliculas/:id` | Obtener película por ID | `http://localhost:3000/peliculas/684b5bc648f3b1c63ff28829` |
| `POST` | `/peliculas` | Crear nueva película | `http://localhost:3000/peliculas` |
| `PATCH` | `/peliculas/:id` | Actualizar película | `http://localhost:3000/peliculas/684b5bc648f3b1c63ff28829` |
| `DELETE` | `/peliculas/:id` | Eliminar película | `http://localhost:3000/peliculas/684b5bc648f3b1c63ff28829` |

### 🔍 Endpoints de Filtrado

<details>
<summary><strong>Ver endpoints de filtrado avanzado</strong></summary>

| Método | Endpoint | Descripción | Ejemplo |
|--------|----------|-------------|---------|
| `GET` | `/peliculas?genero=:genre` | Filtrar por género | `http://localhost:3000/peliculas?genero=Romance` |
| `GET` | `/peliculas/director/:director` | Filtrar por director | `http://localhost:3000/peliculas/director/Christopher%20Nolan` |
| `GET` | `/peliculas/rate/:rate` | Filtrar por puntuación mínima | `http://localhost:3000/peliculas/rate/8.5` |

</details>

### 📊 Códigos de Respuesta HTTP

| Código | Estado | Descripción | Cuándo se usa |
|--------|--------|-------------|---------------|
| `200` | ✅ **OK** | Operación exitosa | GET, PATCH exitosos |
| `201` | ✅ **Created** | Recurso creado exitosamente | POST exitoso |
| `400` | ❌ **Bad Request** | Datos inválidos o faltantes | Validación fallida |
| `404` | ❌ **Not Found** | Película no encontrada | ID inexistente |
| `422` | ❌ **Unprocessable Entity** | Error de validación de Mongoose | Datos no válidos |
| `500` | ❌ **Internal Server Error** | Error del servidor | Problemas de BD o servidor |

> [!NOTE]  
> Todos los endpoints devuelven JSON con la estructura: `{"data": [...], "message": "..."}` para respuestas exitosas y `{"error": "...", "status": number}` para errores.

---

## 📊 Modelo de Datos

> [!NOTE]  
> El esquema de datos está definido en `models/movie.js` usando **Mongoose**.

<details>
<summary><strong>🎬 Estructura del modelo Movie</strong></summary>

```javascript
{
  title: {
    type: String,
    required: true          // ✅ Campo obligatorio
  },
  year: {
    type: Number,
    required: true          // ✅ Campo obligatorio
  },
  director: {
    type: String,
    required: true          // ✅ Campo obligatorio
  },
  duration: {
    type: Number,
    required: true          // ✅ Campo obligatorio (en minutos)
  },
  poster: {
    type: String            // 🔗 URL del poster (opcional)
  },
  genre: {
    type: [String],
    required: true          // ✅ Array de géneros obligatorio
  },
  rate: {
    type: Number,
    required: false,
    default: 5              // ⭐ Puntuación por defecto: 5
  }
}
```

### Ejemplo de película válida:
```json
{
  "title": "The Dark Knight",
  "year": 2008,
  "director": "Christopher Nolan",
  "duration": 152,
  "poster": "https://example.com/poster.jpg",
  "genre": ["Action", "Crime", "Drama"],
  "rate": 9.0
}
```

</details>

---

## 🧪 Pruebas con API HTTP

> [!TIP]  
> Utiliza el archivo `api.http` incluido para probar todos los endpoints fácilmente.

<details>
<summary><strong>📝 Ejemplos de peticiones HTTP</strong></summary>

### ➕ Crear una nueva película
```http
POST http://localhost:3000/peliculas/
Content-Type: application/json

{
    "title": "Mi película con Mongoose",
    "year": 2024,
    "director": "Tu Nombre",
    "duration": 120,
    "genre": ["Action", "Drama", "Crime"]
}
```

### ✏️ Actualizar una película existente
```http
PATCH http://localhost:3000/peliculas/6851fed7cb30539e30ee7f9b
Content-Type: application/json

{
    "duration": 222,
    "year": 2025
}
```

### 🗑️ Eliminar una película
```http
DELETE http://localhost:3000/peliculas/6851f6ea8fb013ee9ba1a276
```

</details>

---

## 🔧 Scripts Disponibles

| Script | Comando | Descripción |
|--------|---------|-------------|
| **Desarrollo** | `pnpm dev` | Inicia el servidor con hot reload |
| **Producción** | `pnpm start` | Inicia el servidor en modo producción |
| **Test** | `pnpm test` | Ejecuta las pruebas (pendiente implementar) |

---

## 📝 Lista de Tareas del Proyecto

### 🚀 Funcionalidades Básicas
- [x] Configuración inicial del proyecto con Express y Mongoose
- [x] Modelo de datos para películas con validación
- [x] Endpoints CRUD completos (GET, POST, PATCH, DELETE)
- [x] Filtrado por género, director y puntuación
- [x] Conexión a MongoDB con variables de entorno
- [x] Estructura MVC implementada
- [x] Documentación completa con diagrama de arquitectura

### 🔍 Mejoras Pendientes
- [ ] Implementar sistema de autenticación JWT
- [ ] Agregar validación de entrada más robusta
- [ ] Implementar paginación para listado de películas
- [ ] Agregar endpoint de búsqueda por título
- [ ] Implementar rate limiting
- [ ] Agregar logging con Winston
- [ ] Implementar tests unitarios con Jest
- [ ] Agregar tests de integración
- [ ] Implementar manejo de errores centralizado
- [ ] Agregar endpoint para subir imágenes de posters

### 🛡️ Seguridad y Producción
- [ ] Implementar helmet para headers de seguridad
- [ ] Agregar validación de CORS
- [ ] Implementar compresión de respuestas
- [ ] Configurar variables de entorno para producción
- [ ] Implementar backup automático de base de datos
- [ ] Configurar SSL/TLS
- [ ] Implementar monitoreo de la aplicación
- [ ] Agregar documentación de API con Swagger

### 📊 Funcionalidades Avanzadas
- [ ] Implementar sistema de favoritos
- [ ] Agregar comentarios y reseñas
- [ ] Implementar sistema de calificaciones por usuarios
- [ ] Agregar recomendaciones basadas en géneros
- [ ] Implementar cache con Redis
- [ ] Agregar notificaciones push
- [ ] Implementar API GraphQL como alternativa
- [ ] Agregar soporte para múltiples idiomas

### 🧪 Testing y Calidad
- [ ] Configurar ESLint y Prettier
- [ ] Implementar pre-commit hooks con Husky
- [ ] Agregar coverage de tests
- [ ] Implementar tests de performance
- [ ] Configurar CI/CD pipeline
- [ ] Agregar análisis de código estático

---

## ⚡ Tecnologías

<details>
<summary><strong>🛠️ Stack tecnológico utilizado</strong></summary>

### Backend
- **[Node.js](https://nodejs.org/)** - Runtime de JavaScript
- **[Express.js](https://expressjs.com/)** - Framework web minimalista
- **[Mongoose](https://mongoosejs.com/)** - ODM para MongoDB

### Base de Datos
- **[MongoDB](https://www.mongodb.com/)** - Base de datos NoSQL

### Herramientas de Desarrollo
- **[pnpm](https://pnpm.io/)** - Gestor de paquetes eficiente
- **Node --watch** - Hot reload nativo de Node.js

### Dependencias principales
```json
{
  "express": "^5.1.0",
  "mongoose": "^8.16.0"
}
```

</details>

---

## 📝 Notas Importantes

> [!IMPORTANT]  
> **Configuración de base de datos:** Asegúrate de que MongoDB esté ejecutándose antes de iniciar la aplicación.

> [!WARNING]  
> **Variables de entorno:** No subas tu archivo `.env` al repositorio. Usa `.env.example` para documentar las variables necesarias.

> [!CAUTION]  
> **Producción:** Esta configuración está pensada para desarrollo. Para producción, considera implementar:
> - Autenticación y autorización
> - Rate limiting
> - Validación de entrada más robusta
> - Logging avanzado
> - Manejo de errores mejorado

<details>
<summary><strong>🔍 Detalles técnicos adicionales</strong></summary>

### Controladores
El proyecto incluye dos versiones de controladores:
- `controllers/movies.js` - Implementación síncrona
- `controllers/moviesPromesas.js` - Implementación con promesas (en uso)

### Middleware
- `express.json()` - Parser de JSON para las peticiones POST/PATCH

### Estructura de respuestas
```javascript
// Respuesta exitosa
{
  "data": [...],
  "message": "Operación exitosa"
}

// Respuesta de error
{
  "error": "Descripción del error",
  "status": 400
}
```

</details>

---

## 🤝 Contribución

> [!NOTE]  
> ¡Las contribuciones son bienvenidas! Por favor, sigue estas pautas:

1. 🍴 Haz fork del proyecto
2. 🌿 Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. 💾 Commit tus cambios (`git commit -am 'Añade nueva funcionalidad'`)
4. 📤 Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. 🔄 Abre un Pull Request

---

<div align="center">

### 🎬 ¡Disfruta gestionando tu colección de películas! 🍿

**Desarrollado con ❤️ usando Node.js, Express y MongoDB**

---

*¿Encontraste algún bug o tienes una sugerencia? ¡Abre un issue!* 🐛

</div>
