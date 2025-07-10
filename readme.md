# API de Peliculas con Mongoose y Express

## Descripción

Este proyecto es una **API REST** de Peliculas con Mongoose y Express. Esta API permite a los usuarios crear, leer, actualizar y eliminar peliculas en la base de datos. Utiliza **Node.js**, **Express**, **Mongoose**, y **MongoDB** para construir esta API.

---

## Tabla de Contenidos

- [🎬 API de Películas con Mongoose y Express](#-api-de-películas-con-mongoose-y-express)
  - [📋 Tabla de Contenidos](#-tabla-de-contenidos)
  - [✨ Características](#Características)
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
  - [📊 Modelo de Datos](#-modelo-de-datos)
    - [Ejemplo de película válida:](#ejemplo-de-película-válida)
  - [🧪 Pruebas con API HTTP](#-pruebas-con-api-http)
    - [➕ Crear una nueva película](#-crear-una-nueva-película)
    - [✏️ Actualizar una película existente](#️-actualizar-una-película-existente)
    - [🗑️ Eliminar una película](#️-eliminar-una-película)
  - [🔧 Scripts Disponibles](#-scripts-disponibles)
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

---

## Características

- ✅ **CRUD Completo** para gestión de películas
- 🔍 **Filtrado avanzado** por género, director y puntuación
- 🗃️ **Base de datos MongoDB** con Mongoose ODM
- 🏗️ **Arquitectura MVC** bien estructurada
- 🚀 **Hot reload** en desarrollo
- 📡 **RESTful API** siguiendo mejores prácticas
- 🔧 **Validación** de datos con Mongoose schemas
