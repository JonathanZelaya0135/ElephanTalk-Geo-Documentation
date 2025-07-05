# Geolocalización

ElephanTalk ahora permite agregar la **ubicación** a tus posts! En esta sección se encuentra todo lo relacionado a la geolocalización.

## Funcionalidades de Geolocalización

### Agregar Ubicación a Posts
- Checkbox opcional "Add my location to this post"
- Obtención automática de coordenadas del dispositivo
- Mapa interactivo para selección manual de ubicación
- Almacenamiento de datos de país y ciudad

### Clasificación de Posts
- **Cerca de ti**: Posts publicados en tu zona local
- **Todo El Salvador**: Todos los posts del país
- Clasificación automática basada en ubicación del usuario

## Detalles Técnicos del Frontend

### Obtener Ubicación del Usuario

Para obtener los detalles de la ubicación actual del dispositivo se hace uso de la Geolocation API por parte del navegador:

```javascript
// Obtener ubicación del usuario
useEffect(() => {
  const getUserLocation = async () => {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(
        (position) => {
          setUserLocation({
            lat: position.coords.latitude,
            lng: position.coords.longitude
          });
        }
      );
    } else {
      console.error("Geolocation is not supported by this browser.");
    }
  };

  getUserLocation();
}, []);
```

### Proceso de Creación de Post con Ubicación

1. **Activar Geolocalización**: Al crear un post, marcar el checkbox *Add my location to this post*
2. **Otorgar Permisos**: El navegador solicita permisos para acceder a la ubicación
3. **Visualización en Mapa**: Se abre un mapa con marcador automático en la ubicación actual
4. **Selección Manual**: Opción de cambiar la ubicación haciendo click en otra parte del mapa

### Separación y Clasificación de Posts

```javascript
// Clasificar posts cuando cambian los posts o la ubicación
useEffect(() => {
  if (!userLocation || !posts.length) return;

  const classifyPosts = async () => {
    const local = [];
    const global = [];
    let City, Country;

    await fetch(`${PhotonAPI}/reverse?lat=${userLocation.lat}&lon=${userLocation.lng}&radius=0.1`)
      .then(response => response.json())
      .then(data => {
        if (data.features.length > 0) {
          setUserCity(data.features[0].properties.city);
          setUserCountry(data.features[0].properties.country);
          City = data.features[0].properties.city;
          Country = data.features[0].properties.country;
        }
      });

    posts.forEach(post => {
      if (!post.country && !post.city) {
        global.push(post);
      } else if (post.country === Country && post.city === City) {
        local.push(post);
        global.push(post);
      } else {
        global.push(post);
      }
    });

    setLocalPosts(local);
    setGlobalPosts(global);
    setIsLoading(false);
  };

  classifyPosts();
}, [posts, userLocation]);
```

### Lógica de Clasificación

El sistema obtiene los datos de ubicación del usuario para generar un radio que se considera *"Cerca de ti"*:

- Identifica la ciudad del usuario
- Clasifica posts según sus datos de ubicación
- Separa posts en categorías: cercanos y globales

## Detalles Técnicos del Backend

### Estructura de Datos

Los posts ahora incluyen información de ubicación opcional:

**Post con ubicación:**
```json
{
  "_id": "6860f0812d66868463aaa3364",
  "description": "ANUIDNUAIWNDU9AWH9DAW",
  "image": "https://i.imgflip.com/9mj9dy.jpg",
  "location": {
    "country": "El Salvador",
    "city": "San Salvador"
  },
  "active": true,
  "manualReviewed": false,
  "user": "6860e4dd2d66868463aa327d",
  "likes": [],
  "comments": [],
  "createdAt": "2025-06-29T07:51:29.431+00:00",
  "updatedAt": "2025-06-29T07:51:29.431+00:00",
  "__v": 0
}
```

**Post sin ubicación:**
```json
{
  "_id": "6860e8ec2d66868463aa32ac",
  "description": "Happening",
  "image": "https://i.imgflip.com/9mj9dy.jpg",
  "location": {
    "country": null,
    "city": null
  },
  "active": true,
  "manualReviewed": false,
  "user": "6860e4ddd2d66868463aa327d",
  "likes": [],
  "comments": [],
  "createdAt": "2025-06-29T07:19:08.540+00:00",
  "updatedAt": "2025-06-29T07:19:08.540+00:00",
  "__v": 0
}
```

### Características del Manejo de Ubicación

- **Opcional**: Agregar ubicación es completamente opcional
- **Campos null**: Los posts pueden tener campos de ubicación nulos
- **Flexibilidad**: El sistema maneja tanto posts con ubicación como sin ella
- **Consistencia**: Estructura de datos uniforme para todos los posts

## Integración con PhotonAPI

### Propósito
- Conversión de coordenadas a información geográfica legible
- Geocodificación inversa para obtener país y ciudad
- Clasificación automática de posts por proximidad

### Configuración
- URL configurada en variables de entorno: `VITE_PHOTON_API_URL`
- Servicio independiente ejecutándose en puerto 2322
- Parámetro radius para definir área de proximidad

## Interfaz de Usuario

### Secciones de Posts

**Cerca de ti:**
- Muestra posts publicados en la zona local del usuario
- Basado en coincidencia de ciudad y país

**Todo El Salvador:**
- Muestra todos los posts del país
- Incluye tanto posts locales como de otras ubicaciones

### Experiencia del Usuario

- **Permisos claros**: Solicitud transparente de permisos de ubicación
- **Control manual**: Posibilidad de seleccionar ubicación diferente
- **Feedback visual**: Mapa interactivo con marcadores
- **Clasificación automática**: Separación inteligente de contenido por proximidad