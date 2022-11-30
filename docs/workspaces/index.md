import wsconfig from './wsconfig.png';
import workspaces from './workspaces.png';

# Workspaces

Los **Workspaces** son ambientes virtuales que se ejecutan dentro de un clúster de **Kubernetes**, donde se ejecutan tus aplicaciones y estas interactuán entre si en forma de microservicios.

En el menú principal da click en [Workspaces](https://beta.serpa.cloud/dashboard/projects/envs), donde podrás ver el listado de Workspaces existentes.

<img src={workspaces} alt="Workspaces" />

## Crear un workspace

1. En el menú principal da click en [Workspaces](https://beta.serpa.cloud/dashboard/projects/envs).
2. Da click en el botón [Crear un workspace](https://beta.serpa.cloud/dashboard/projects/envs/create).
3. Agrega un Avatar a tu Workspace (Opcional).
4. Agrega un nombre y una descripción corta a tu Worspace.
5. Selecciona el clúster en el que se va a crear el Worspace, en el dropdown solo aparecen Clústeres creados, por lo que si acabas de crear un clúster es necesario esperar de 10 - 15 minutos.
6. Agrega variables de entorno que se aplicarán a todas las cargas de trabajo que se ejecuten en el workspace (Opcional). Para más información visita [Precedencia de variables de entorno y sobreescritura](/docs/others/env-vars).
7. Da click en **Guardar**.

## Detalle de un workspace

Para ver el detalle de un Workspace y trabajar sobre el:

1. En el menú principal da click en [Workspaces](https://beta.serpa.cloud/dashboard/projects/envs).
2. Da click en el workspace deseado.

## Editar un workspace

1. En el menú principal da click en [Workspaces](https://beta.serpa.cloud/dashboard/projects/envs).
2. Da click en el workspace deseado.
3. Da click en la sección **Configuraciones**.

<img src={wsconfig} alt="Editar workspace" />
