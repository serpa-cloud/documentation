# Crear una app

:::tip

Antes de crear una app aseguráte de leer la información sobre como conectar [Repositorios git](/docs/others/git-repos)

:::

Para crear una app, sigue los siguientes pasos:

1. Abre la consola de [Apps](https://beta.serpa.cloud/dashboard/projects/apps).
2. Haz click en el botón [Crear una app](https://beta.serpa.cloud/dashboard/projects/apps/create).
3. Agrega un logo o avatar para tu aplicación (Opcional).
4. Agrega un nombre para identificar tu aplicación.
5. Haz click en el selector **Repositorio git** y selecciona un repositorio (para más información sobre conectar repositorios visita [Repositorios git](/docs/others/git-repos)).
6. Serpa se basa en contenedores [Docker](https://www.docker.com/), por lo que para compilar la imágen es necesario definir un [Dockerfile](https://docs.docker.com/engine/reference/builder/), para hacerlo puedes:
   - Crear un archivo Dockerfile en la raíz de tu proyecto.
   - Ó prender el slider **Usar una plantilla de Dockerfile**, hacer click en el selector **Dockerfile**, seleccionar una de las plantillas predefinidas, revisar el contenido del template y dar click en **Seleccionar**.
7. En caso de que lo desees, habilita el proceso de **Continous interation**, para más información visita [CI / CD](/docs/others/ci-cd) (Opcional).
8. Si tu aplicación usa **variables de entorno** y deseas que se apliquen en todas las compilaciones y ejecuciones de tu app, definelas aquí, para más información visita [Precedencia de variables de entorno y sobreescritura](/docs/others/env-vars).
9. Haz click en **Guardar**.
