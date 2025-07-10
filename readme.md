# API de Peliculas con Mongoose y Express

## Descripción

Este proyecto es una **API REST** de Peliculas con Mongoose y Express. Esta API permite a los usuarios crear, leer, actualizar y eliminar peliculas en la base de datos. Utiliza **Node.js**, **Express**, **Mongoose**, y **MongoDB** para construir esta API.

---

## 📋 Tabla de Contenidos

- [API de Peliculas con Mongoose y Express](#api-de-peliculas-con-mongoose-y-express)
  - [Descripción](#descripción)
  - [📋 Tabla de Contenidos](#-tabla-de-contenidos)
  - [✨ Características](#-características)
  - [📝 Lista de Tareas del Proyecto](#-lista-de-tareas-del-proyecto)
    - [🚀 Funcionalidades Básicas](#-funcionalidades-básicas)
    - [🔍 Mejoras Pendientes](#-mejoras-pendientes)
    - [🛡️ Seguridad y Producción](#️-seguridad-y-producción)
    - [📊 Funcionalidades Avanzadas](#-funcionalidades-avanzadas)
    - [🧪 Testing y Calidad](#-testing-y-calidad)
  - [🔧 Scripts Disponibles](#-scripts-disponibles)
  - [📡 Endpoints de la API](#-endpoints-de-la-api)
    - [🎯 Operaciones CRUD Básicas](#-operaciones-crud-básicas)
    - [🔍 Endpoints de Filtrado](#-endpoints-de-filtrado)
    - [📊 Códigos de Respuesta HTTP](#-códigos-de-respuesta-http)
  - [📊 Modelo de Datos](#-modelo-de-datos)
    - [Ejemplo de película válida:](#ejemplo-de-película-válida)

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
## 🔧 Scripts Disponibles

| Script | Comando | Descripción |
|--------|---------|-------------|
| **Desarrollo** | `pnpm dev` | Inicia el servidor con hot reload |
| **Producción** | `pnpm start` | Inicia el servidor en modo producción |
| **Test** | `pnpm test` | Ejecuta las pruebas (pendiente implementar) |

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
