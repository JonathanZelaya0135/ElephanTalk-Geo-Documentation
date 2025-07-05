# Moderación de Contenido

ElephanTalk implementa un sistema avanzado de moderación de contenido que combina análisis automático con revisión humana para mantener un ambiente seguro y respetuoso.

## Características Principales

### Análisis Automático con Detoxify

ElephanTalk integra el modelo de aprendizaje automático **Detoxify**, reconocido en la comunidad de código abierto por su capacidad para analizar y detectar contenido tóxico en texto.

#### Funcionalidades de Detoxify:
- **Análisis en tiempo real**: Examina el tono y contenido de mensajes instantáneamente
- **Detección de toxicidad**: Identifica contenido abusivo, insultante o discriminatorio
- **Categorización automática**: Clasifica diferentes tipos de contenido problemático
- **Respuesta inmediata**: Proporciona retroalimentación rápida ante contenido inapropiado

### Sistema Híbrido de Moderación

La moderación en ElephanTalk combina:

1. **Análisis Automático**: Detoxify procesa todo el contenido
2. **Revisión Humana**: Moderadores verifican casos complejos
3. **Reportes de Usuario**: La comunidad puede reportar contenido inapropiado

## Arquitectura de Moderación

### Microservicio FastAPI

- **Propósito**: Manejo especializado del modelo Detoxify
- **Tecnología**: FastAPI con Python 3.10
- **Integración**: Conectado con la API principal de NestJS
- **Rendimiento**: Optimizado para análisis rápido de texto

### Configuración de Toxicidad

```plaintext
TOXICITY_URL="http://fastapi-service:8000"
TOXICITY_THRESHOLD=0.25
```

- **Threshold**: Umbral de toxicidad configurable (0.25 por defecto)
- **URL**: Endpoint del microservicio FastAPI
- **Escalabilidad**: Servicio independiente para mejor rendimiento

## Proceso de Moderación

### Flujo Automático

1. **Publicación**: Usuario crea contenido (post, comentario)
2. **Análisis**: Detoxify analiza el texto automáticamente
3. **Evaluación**: Se compara contra el umbral configurado
4. **Acción**: Contenido se aprueba o marca para revisión

### Flujo de Revisión Manual

1. **Detección**: Contenido marcado por análisis automático o reporte de usuario
2. **Queue**: Contenido entra en cola de moderación
3. **Revisión**: Moderador humano evalúa el contenido
4. **Decisión**: Aprobación, edición o eliminación del contenido

### Sistema de Reportes

Los usuarios pueden reportar contenido que consideren inapropiado:

- **Reportes de usuario**: Funcionalidad para denunciar contenido
- **Verificación manual**: Moderadores revisan todos los reportes
- **Gestión de sutilezas**: Captura contenido que el análisis automático podría pasar por alto

## Funcionalidades Avanzadas

### Validación Automática

- **Comentarios**: Análisis automático antes de publicación
- **Publicaciones**: Verificación de contenido de posts
- **Tiempo real**: Procesamiento instantáneo durante la creación

### Gestión de Moderación

- **Panel de moderación**: Interfaz especializada para moderadores
- **Aplicación separada**: https://elephantalk-moderation.vercel.app
- **Herramientas**: Revisión, aprobación y gestión de contenido

## Beneficios del Sistema

### Para la Comunidad

- **Ambiente seguro**: Libre de toxicidad común en redes sociales
- **Expresión libre**: Los usuarios pueden expresarse con seguridad
- **Respeto mutuo**: Promoción de interacciones constructivas
- **Calidad de contenido**: Mantenimiento de estándares comunitarios

### Para los Moderadores

- **Eficiencia**: Análisis automático reduce carga de trabajo
- **Precisión**: Combinación de IA y revisión humana
- **Herramientas**: Interfaz dedicada para gestión
- **Escalabilidad**: Sistema que crece con la comunidad

## Integración Técnica

### Frontend Principal

- **Feedback en tiempo real**: Indicadores de estado de moderación
- **Interfaz limpia**: Ocultación de contenido problemático
- **Notificaciones**: Alertas sobre acciones de moderación

### Backend NestJS

- **Orchestración**: Coordina entre servicios de moderación
- **Gestión de estados**: Manejo de estados de posts y comentarios
- **Integración**: Comunicación con microservicio FastAPI

### Base de Datos

```javascript
// Campos de moderación en posts
{
  "active": true,           // Estado activo del post
  "manualReviewed": false,  // Indica si fue revisado manualmente
  // ... otros campos
}
```

## Configuración de Moderación

### Variables de Entorno

```plaintext
# Configuración de toxicidad
TOXICITY_URL="http://fastapi-service:8000"
TOXICITY_THRESHOLD=0.25

# Configuración de moderación
MODERATION_ENABLED=true
AUTO_REVIEW_ENABLED=true
```

### Personalización

- **Umbral ajustable**: Configuración del nivel de sensibilidad
- **Categorías**: Diferentes tipos de contenido problemático
- **Reglas**: Configuración de reglas específicas de moderación

## Monitoreo y Métricas

### Análisis de Efectividad

- **Tasa de detección**: Porcentaje de contenido tóxico identificado
- **Falsos positivos**: Contenido legítimo marcado incorrectamente
- **Tiempo de respuesta**: Velocidad de procesamiento de moderación
- **Satisfacción del usuario**: Feedback sobre la calidad de moderación

### Mejora Continua

- **Ajuste de parámetros**: Optimización basada en resultados
- **Entrenamiento**: Actualización del modelo con nuevos datos
- **Feedback loop**: Incorporación de decisiones de moderadores humanos