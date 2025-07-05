# Stack Tecnológico

Para el desarrollo de ElephanTalk, se seleccionaron diversas herramientas y tecnologías que facilitan la creación, prueba y despliegue de la plataforma.

## Frontend

### React.js

- **Versión**: v17.0.2
- **Uso**: Biblioteca principal para construir la interfaz de usuario
- **Características**: Componentes interactivos y reutilizables, gestión eficiente del estado
- **Beneficios**: Desarrollo declarativo, gran ecosistema, amplia comunidad

### Vite

- **Versión**: v2.6
- **Uso**: Herramienta de construcción de frontend
- **Características**: Reinicio instantáneo del servidor, bundling optimizado
- **Beneficios**: Desarrollo más rápido, mejores tiempos de construcción

### Tailwind CSS

- **Versión**: v2.2
- **Uso**: Framework de CSS utilitario
- **Características**: Diseño responsivo, componentes personalizables
- **Beneficios**: Desarrollo rápido de interfaces, diseño coherente

## Backend

### NestJS

- **Versión**: v8.0
- **Uso**: Framework principal para la API
- **Características**: TypeScript nativo, arquitectura modular, decoradores
- **Beneficios**: Escalabilidad, mantenibilidad, testing integrado

**Características destacadas:**

- Programación Orientada a Objetos (POO)
- Programación Funcional
- Programación Reactiva
- Inyección de dependencias nativa

### FastAPI

- **Versión**: v0.65.2
- **Uso**: Microservicio para análisis de toxicidad con Detoxify
- **Características**: Alto rendimiento, documentación automática, validación de tipos
- **Beneficios**: APIs rápidas y robustas, desarrollo moderno con Python 3.7+

## Base de Datos

### MongoDB

- **Versión**: v4.4
- **Uso**: Base de datos principal NoSQL
- **Características**: Documentos JSON, escalabilidad horizontal, consultas flexibles
- **Beneficios**: Alta performance, alta disponibilidad, fácil escalabilidad

### Mongoose

- **Versión**: v5.13.8
- **Uso**: ODM (Object Document Mapping) para MongoDB
- **Características**: Esquemas definidos, validación, middleware
- **Beneficios**: API sencilla, modelación robusta de datos

## Inteligencia Artificial

### Detoxify

- **Uso**: Detección de contenido tóxico en tiempo real
- **Características**: Modelo pre-entrenado, múltiples categorías de toxicidad
- **Integración**: A través del microservicio FastAPI
- **Beneficios**: Moderación automática, ambiente seguro para usuarios

## Servicios Externos

### PhotonAPI

- **Uso**: Geocodificación reversa para funcionalidad de ubicación
- **Características**: Datos de OpenStreetMap, API REST sencilla
- **Beneficios**: Datos geográficos precisos, servicio gratuito

## Herramientas de Desarrollo

### Control de Versiones

- **Git**: Sistema de control de versiones distribuido
- **Codeberg**: Plataforma de hosting para repositorios Git

### Gestores de Paquetes

- **npm**: Para dependencias de Node.js
- **pip**: Para dependencias de Python

### Contenedores

- **Docker**: Contenedorización de servicios
- **Docker Compose**: Orquestación de múltiples contenedores

## Despliegue

### Frontend

- **Vercel**: Plataforma de despliegue para aplicaciones frontend
- **URLs de producción**:
  - Aplicación principal: https://elephantalk.vercel.app
  - Panel de moderación: https://elephantalk-moderation.vercel.app

### Backend

- **Docker**: Para encapsular servicios
- **Configuración mediante variables de entorno**

## Justificación de la selección

Estas herramientas y tecnologías han sido escogidas por:

- **Robustez y escalabilidad**: Capacidad de manejar carga creciente
- **Compatibilidad**: Fácil integración entre componentes
- **Comunidad activa**: Soporte continuo y documentación abundante
- **Desarrollo moderno**: Uso de las mejores prácticas actuales
- **Mantenimiento sencillo**: Arquitectura clara y bien documentada

Esta combinación tecnológica asegura un desarrollo fluido y un mantenimiento sencillo de ElephanTalk, preparando la plataforma para futuras expansiones y mejoras.
