# Modelo de Datos

ElephanTalk utiliza MongoDB, una base de datos NoSQL, que permite flexibilidad en la estructura de datos y escalabilidad horizontal.

## Diagrama del modelo de datos original

![Diagrama de base de datos sin relaciones](https://github.com/kevocodes/ElephanTalk/assets/62626446/a8e9fa4e-9233-4ae6-b189-5d2a4d809b90)

## Modificaciones al modelo de datos

### Post

Los posts son el contenido principal de la plataforma. La nueva estructura incluye soporte para geolocalización opcional.

El modelo de datos de los posts es el único que se ha modificado para la implementación de la geolocalización de los posts publicados. La modificación realizada fue que se agrego el campo *location* de tipo objeto para almacenar los datos de *País* y *Ciudad* luego de ser procesados por el servicio de **PhotonAPI**, mandando asi los posts directamente a la sección. Adicionálmente, debido a que agregar la ubicación es completamente opcional, estos campos pueden ser de tipo *null*. El siguiente es un ejemplo de la nueva estructura implementada:


```json
{
  "_id": "6860f0812d66868463aaa3364",
  "description": "Contenido del post",
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

## Campos explicados

**Campos principales**

- _id: Identificador único del documento
- description: Contenido textual del post
- image: URL de la imagen adjunta (opcional)
- user: Referencia al usuario que creó el post

**Campos de ubicación**

- location.country: País donde se creó el post (opcional)
- location.city: Ciudad donde se creó el post (opcional)

**Campos de moderación**

- active: Indica si el post está activo y visible
- manualReviewed: Marca si ha sido revisado manualmente por moderadores

**Campos de interacción**

- likes: Array de usuarios que han dado like al post
- comments: Array de comentarios en el post

**Campos de auditoría**

- createdAt: Fecha y hora de creación
- updatedAt: Fecha y hora de última actualización
- __v: Versión del documento (Mongoose)

---

**Ventajas del modelo NoSQL**

- Flexibilidad: Fácil adición de nuevos campos
- Escalabilidad: Distribución horizontal natural
- Performance: Consultas rápidas sin joins complejos
- Desarrollo ágil: Cambios de esquema sin migraciones complejas

---

Este modelo de datos está diseñado para soportar el crecimiento de la plataforma manteniendo la simplicidad y eficiencia en las operaciones más comunes.