# Repositorios git

Cuando haces click en el selector **Repositorio git** en el formulario [Crear una app](https://beta.serpa.cloud/dashboard/projects/apps/create), se abrirá un panel del lado derecho con dos tabs: [Github](#github) y [Gitlab](#gitlab)

:::tip

Cuando conectas tu cuenta de Github o Gitlab a Serpa, esta se asocia solo a tu usuario en Serpa, no a toda tu organización, por lo que mantenemos la privacidad de tus repositorios, soló cuando creas una aplicación, delegas a esa única app el permiso para interactuar con Serpa, pero nunca se exponen tus datos con otras personas o colaboradores.

:::

## Github

Para conectar una cuenta de Github:

1. Selecciona el tab Github.
2. Da click en el botón **Conectar a Github**.
3. Se abrirá una nueva ventana de Github, donde podrás seleccionar las organizaciones que quieres conectar con Serpa. Los repositorios asociados a tu cuenta personal siempre se conectan por defecto.
4. Da click en **Guardar / Aceptar**, regresarás a Serpa donde se listarán todos los repositorios a los que diste acceso.
5. Da **check** en el repositorio que quieras usar como código fuente de tu aplicación.

## Gitlab

Para conectar una cuenta de Gitlab:

1. Selecciona el tab Gitlab.
2. Ingresa tu usuario de Gitlab.
3. Ingresa al menú [Personal tokens](https://gitlab.com/-/profile/personal_access_tokens) en Gitlab.
4. Crea un token con los siguientes scopes:
   - api
   - read_api
   - read_user
   - read_repository
5. Copia el token y pegalo en Serpa.
6. Da click en el botón **Conectar a Gitlab**, automaticamente se listarán todos los repositorios a los que diste acceso.
7. Da **check** en el repositorio que quieras usar como código fuente de tu aplicación.
