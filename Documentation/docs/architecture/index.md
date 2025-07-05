# Arquitectura del Sistema

ElephanTalk implementa una arquitectura moderna y escalable que combina buenas prácticas de desarrollo frontend y backend.

## Visión general de la arquitectura

La plataforma está construida con una arquitectura de microservicios que incluye:

- **Frontend principal**: Aplicación React para usuarios
- **Panel de moderación**: Interfaz administrativa separada  
- **API principal**: Servicio NestJS con MongoDB
- **Servicio de moderación**: Microservicio FastAPI con modelo Detoxify
- **Servicio de geolocalización**: PhotonAPI para datos de ubicación

## Componentes principales

### Frontend
- **React.js**: Biblioteca principal para la interfaz de usuario
- **Tailwind CSS**: Framework de estilos utilitarios
- **Vite**: Herramienta de construcción rápida

### Backend
- **NestJS**: Framework principal para la API
- **MongoDB + Mongoose**: Base de datos NoSQL con ODM
- **FastAPI**: Microservicio para análisis de toxicidad

### Servicios externos
- **Detoxify**: Modelo de ML para detección de contenido tóxico
- **PhotonAPI**: Servicio de geocodificación reversa

## Ventajas de esta arquitectura

- **Escalabilidad**: Cada servicio puede escalarse independientemente
- **Mantenibilidad**: Separación clara de responsabilidades
- **Flexibilidad**: Fácil integración de nuevos servicios
- **Rendimiento**: Optimizada para respuestas rápidas

## Próximos pasos

- [Patrones de diseño implementados](design-patterns.md)
- [Modelo de datos](data-model.md)
- [Stack tecnológico detallado](software-stack.md)