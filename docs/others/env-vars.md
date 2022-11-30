# Precedencia de variables de entorno y sobreescritura

Para crear una app, sigue los siguientes pasos:

:::tip

Antes de crear una app aseguráte de leer la información sobre como conectar [Repositorios git](/docs/apps/git-repos)

:::

1. Abre la consola de [Apps](https://beta.serpa.cloud/dashboard/projects/apps).
2. Haz click en el botón [Crear una app](https://beta.serpa.cloud/dashboard/projects/apps/create).
3. Agrega un logo o avatar para tu aplicación (Opcional).
4. Agrega un nombre para identificar tu aplicación.
5. Haz click en el selector **Repositorio git** y selecciona un repositorio (para más información sobre conectar repositorios visita [Repositorios git](/docs/apps/git-repos)).
6. Serpa se basa en contenedores [Docker](https://www.docker.com/), por lo que para compilar la imágen es necesario definir un [Dockerfile](https://docs.docker.com/engine/reference/builder/), para hacerlo puedes:
   - Crear un archivo Dockerfile en la raíz de tu proyecto.
   - Ó prender el slider **Usar una plantilla de Dockerfile**, hacer click en el selector **Dockerfile**, seleccionar una de las plantillas predefinidas, revisar el contenido del template y dar click en **Seleccionar**.
7. En caso de que lo desees, habilita el proceso de **Continous interation**, para más información visita [CI / CD](/docs/apps/ci-cd) (Opcional).
8. Si tu aplicación usa **variables de entorno** y deseas que se apliquen en todas las compilaciones y ejecuciones de tu app, definelas aquí, para más información visita [Precedencia de variables de entorno y sobreescritura](/docs/apps/env-vars).

## Casos de uso

Usando una App en Serpa podrías generar cualquier tipo de _microservicio_, _webservice_ o servidor, algunos ejemplos:

- Sistema de autenticación escrito en _Java Spring_
- Microservicios de análisis de datos en _Python_
- Pipeline para transformación de imágenes en _NodeJS_
- Sistema de inventarios en _Ruby_
- Ejecutar soluciones pre existentes como _Magento_ o _WordPress_
