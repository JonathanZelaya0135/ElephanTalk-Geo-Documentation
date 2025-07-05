# Configuración del Sistema

Esta sección proporciona guías detalladas para configurar tanto el frontend como el backend de ElephanTalk en tu entorno de desarrollo.

## Visión general

ElephanTalk consiste en múltiples servicios que trabajan juntos:

- **Frontend principal**: Aplicación React para usuarios
- **Panel de moderación**: Interfaz administrativa
- **API NestJS**: Servicio backend principal
- **API FastAPI**: Microservicio de moderación con Detoxify
- **PhotonAPI**: Servicio de geolocalización

## Prerrequisitos

Antes de comenzar, asegúrate de tener instalado:

- [Node.js 20.x](../getting-started/system-requirements.md#nodejs)
- [Python 3.10](../getting-started/system-requirements.md#python)
- [Java 11+](../getting-started/system-requirements.md#java)
- [Docker y Docker Compose](../getting-started/system-requirements.md#contenedores)

## Guías de configuración

### [Frontend](frontend-setup.md)
Configuración de la aplicación React principal y el panel de moderación.

### [Backend](backend-setup.md)  
Configuración de los servicios NestJS y FastAPI con Docker.

### [PhotonAPI](photon-api.md)
Configuración del servicio de geolocalización.

## Orden de configuración recomendado

1. **PhotonAPI**: Configura primero el servicio de geolocalización
2. **Backend**: Levanta los servicios de API 
3. **Frontend**: Configura y ejecuta las aplicaciones React

## URLs de desarrollo por defecto

Una vez configurado correctamente, tendrás acceso a:

- **Frontend principal**: http://localhost:5173
- **Panel de moderación**: http://localhost:5174 (o puerto asignado)
- **API NestJS**: http://localhost:3000
- **API FastAPI**: http://localhost:8000
- **PhotonAPI**: http://localhost:2322

## Solución de problemas

Si encuentras problemas durante la configuración:

1. Verifica que todos los prerrequisitos estén instalados
2. Revisa que los puertos no estén en uso por otros servicios
3. Consulta los logs de cada servicio para errores específicos
4. Asegúrate de que las variables de entorno estén configuradas correctamente