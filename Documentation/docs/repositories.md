# Repositorios

## Estructura del proyecto

Para el desarrollo de este proyecto, se ha modificado la estructura de los repositorios; debido a que no se ha modificado el repositorio de **Frontend Moderación**, por lo tanto ese repositorio se ha mezclado con el de **ElephanTalk Backend** Resultando en un repositorio llamado **ElephanTalk-Backend-Moderation**, La estructura resultante de los repositorios es la siguiente:

[![Frontend](https://badgen.net/badge/Frontend/ElephanTalk%20Principal%20App/blue?icon=https://codeberg.org/Codeberg/Design/raw/branch/main/logo/icon/svg/codeberg-logo_icon_blue.svg)](https://codeberg.org/KevinC911/ElephanTalk-Frontend)

**ElephanTalk Frontend Principal**

- Aplicación principal de usuario
- Desarrollada con React.js y Tailwind CSS

[![Backend-Moderation](https://badgen.net/badge/Backend/ElephanTalk%20API/blue?icon=https://codeberg.org/Codeberg/Design/raw/branch/main/logo/icon/svg/codeberg-logo_icon_blue.svg)](https://codeberg.org/KevinC911/ElephanTalk-Backend-Moderation)

**ElephanTalk Backend-Moderation**

- API principal desarrollada con NestJS
- Microservicio de moderación con FastAPI
- Microservicio de geocoder con PhotonAPI
- Integración con modelo Detoxify
- Panel de administración y moderación
- Interfaz para revisión manual de contenido

Cada repositorio mantiene su propia documentación específica y configuración de despliegue. Para obtener información detallada sobre la configuración de cada componente, consulta la sección de [configuración](setup/index.md).

---

## Estructura original del proyecto

El proyecto original de ElephanTalk está compuesto por tres repositorios principales alojados en Codeberg, los cuales son los siguientes:

[![Frontend](https://badgen.net/badge/Frontend/ElephanTalk%20Principal%20App/blue?icon=https://codeberg.org/Codeberg/Design/raw/branch/main/logo/icon/svg/codeberg-logo_icon_blue.svg)](https://codeberg.org/kevocodes/ElephanTalk-Frontend)

**ElephanTalk Frontend Principal**

- Aplicación principal de usuario
- Desarrollada con React.js y Tailwind CSS
- URL de producción: https://elephantalk.vercel.app

[![Frontend](https://badgen.net/badge/Frontend/ElephanTalk%20Moderation/blue?icon=https://codeberg.org/Codeberg/Design/raw/branch/main/logo/icon/svg/codeberg-logo_icon_blue.svg)](https://codeberg.org/kevocodes/ElephanTalk-Moderation)

**ElephanTalk Moderación**

- Panel de administración y moderación
- Interface para revisión manual de contenido
- URL de producción: https://elephantalk-moderation.vercel.app

[![Backend](https://badgen.net/badge/Backend/ElephanTalk%20API/blue?icon=https://codeberg.org/Codeberg/Design/raw/branch/main/logo/icon/svg/codeberg-logo_icon_blue.svg)](https://codeberg.org/kevocodes/ElephanTalk-Backend)

**ElephanTalk Backend**

- API principal desarrollada con NestJS
- Microservicio de moderación con FastAPI
- Integración con modelo Detoxify
