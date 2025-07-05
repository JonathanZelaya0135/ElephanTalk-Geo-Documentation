# Características de ElephanTalk

ElephanTalk es una plataforma de red social innovadora diseñada específicamente para estudiantes de informática y áreas afines, creada para fomentar la interacción y el intercambio de conocimientos en un entorno seguro y estimulante.

## Características Principales

### [Moderación de Contenido](moderation.md)
- Análisis automático de toxicidad con modelo Detoxify
- Sistema de reportes por usuarios
- Revisión manual por moderadores
- Detección en tiempo real de contenido abusivo

### [Manejo de Errores](error-handling.md)
- Sistema estructurado de seguimiento de errores
- Documentación detallada de problemas y soluciones
- Gestión de issues mediante GitHub Projects

### [Geolocalización](geolocation.md)
- Agregar ubicación a posts
- Clasificación de posts por proximidad ("Cerca de ti" vs "Todo El Salvador")
- Selección manual de ubicación en mapa interactivo
- Integración con PhotonAPI para datos geográficos

## Funcionalidades Adicionales

- **Interfaz dinámica**: Plataforma que promueve activamente la discusión y colaboración
- **Entorno seguro**: Libre de toxicidad común en redes sociales tradicionales
- **Comunidad especializada**: Enfocada en estudiantes de informática y áreas afines
- **Moderación híbrida**: Combinación de análisis automático y revisión humana

## Arquitectura de Características

Las características de ElephanTalk están diseñadas para trabajar de manera integrada:

1. **Frontend React**: Interfaz de usuario interactiva y responsiva
2. **Backend NestJS**: API principal para manejo de datos y lógica de negocio
3. **Microservicio FastAPI**: Análisis de toxicidad especializado
4. **PhotonAPI**: Servicios de geolocalización y mapas

## Próximas Funcionalidades

El sistema está diseñado para ser escalable y permitir la adición de nuevas características de manera sencilla, manteniendo la arquitectura modular y los patrones de diseño establecidos.