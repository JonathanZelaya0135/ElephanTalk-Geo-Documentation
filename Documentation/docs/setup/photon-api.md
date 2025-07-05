# Configuración de PhotonAPI

PhotonAPI es el servicio utilizado para obtener los datos de país y ciudad de los posts basándose en coordenadas geográficas. Este servicio **no está** configurado para ejecutarse en un contenedor de Docker y debe inicializarse manualmente.

## Requisitos

- [Java 11+](https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html)
- Archivo `photon-opensearch-0.7.0.jar`

## Configuración Manual

Para levantar el servicio de PhotonAPI, sigue estos pasos:

### 1. Abrir Command Prompt

Abre una ventana de **Command Prompt (Símbolo del Sistema)** como administrador.

### 2. Ejecutar el Servicio

Ejecuta el siguiente comando en la terminal:

```plaintext
java -jar photon-opensearch-0.7.0.jar -cors-any
```

### 3. Verificar la Configuración

Una vez iniciado, el servicio estará disponible en:

```
http://localhost:2322
```

## Funcionalidad

PhotonAPI se utiliza para:

- **Geocodificación inversa**: Convertir coordenadas (latitud y longitud) en información de ubicación legible (país, ciudad)
- **Clasificación de posts**: Determinar si un post es "Cerca de ti" o "Todo El Salvador"
- **Obtención de datos de ubicación**: Proporcionar información geográfica precisa para las funcionalidades de geolocalización

## Integración con ElephanTalk

### Variables de Entorno

Asegúrate de configurar la URL de PhotonAPI en las variables de entorno del frontend:

```plaintext
VITE_PHOTON_API_URL="http://localhost:2322"
```

### Uso en el Backend

El backend utiliza PhotonAPI para procesar las coordenadas enviadas desde el frontend y convertirlas en datos de ubicación estructurados que se almacenan en la base de datos.

## Resolución de Problemas

### El servicio no inicia

- Verifica que tienes Java 11 o superior instalado
- Asegúrate de que el archivo `photon-opensearch-0.7.0.jar` está en el directorio correcto
- Verifica que el puerto 2322 no esté siendo utilizado por otro servicio

### Errores de CORS

El parámetro `-cors-any` permite todas las solicitudes CORS. Si necesitas mayor seguridad, consulta la [documentación de PhotonAPI](https://photonnetwork.readthedocs.io/en/v1.0.0/rest_api/) para configuraciones más restrictivas.

### Problemas de Conectividad

- Verifica que el servicio esté ejecutándose en `http://localhost:2322`
- Asegúrate de que no hay firewall bloqueando el puerto 2322
- Comprueba que las variables de entorno del frontend apunten a la URL correcta

## Notas Importantes

- PhotonAPI debe estar ejecutándose **antes** de iniciar el frontend y backend de ElephanTalk
- El servicio debe mantenerse activo durante toda la sesión de desarrollo
- Para entornos de producción, considera configurar PhotonAPI como un servicio del sistema operativo o agregarla al conenedor de Docker del backend