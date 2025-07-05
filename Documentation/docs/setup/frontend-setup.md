# Configuración del Frontend

Esta guía te ayudará a configurar tanto la aplicación principal como el panel de moderación de ElephanTalk.

## Variables de entorno

### Archivo .env principal

Copia el archivo `.env.example` y renómbralo a `.env` en el directorio del frontend principal:

```plaintext
# URL base de la API pública
VITE_PUBLIC_API_URL=""

# Cantidad de publicaciones por página para desplazamiento infinito
VITE_POSTS_PER_PAGE=10

# URL PhotonAPI
VITE_PHOTON_API_URL=""
```

### Configuración de valores

- VITE_PUBLIC_API_URL: URL de tu API NestJS (por defecto: ```http://localhost:3000```)
- VITE_POSTS_PER_PAGE: Número de posts a cargar por vez (recomendado: 10)
- VITE_PHOTON_API_URL: URL de PhotonAPI (por defecto: ```http://localhost:2322```)

### Instalación de dependencias

```bash
# Navegar al directorio del frontend
cd frontend-directory

# Instalar dependencias
npm install

# o
yarn install
```

### Testing
```bash
# Unit testing
$ yarn run test

# e2e testing
$ yarn run test:e2e

# e2e testing with UI
$ yarn run test:e2e:open
```

Para levantar el servicio en desarrollo:
```bash
npm run dev
```