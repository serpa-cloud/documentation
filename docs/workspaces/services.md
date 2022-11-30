import services from './services.png';
import internal from './internal.png';

# Servicios

Antes de empezar a ejecutar tus aplicaciones, es necesario crear un servicio que exponga el acceso de red a las distintas cargas de trabajo de una app.

<img src={services} alt="Servicios" />

## Crear un servicio

Para implementar un servicio:

1. Accede a la sección **Servicios** en el detalle de un **Workspace**.
2. Da click en el botón **Crea un servicio**.
3. En el dropdown selecciona la app a la que quieres crear un servicio.
4. Da click en **Guardar**.

## Comunicación interna entre servicios

Cuando quieres comunicarte entre los distintos servicios de un workspace, puedes hacer peticiones por la red interna del workspace, sin necesidad de salir a internet, para hacerlo cada servicio muestra su url interna:

1. Accede a la sección **Servicios** en el detalle de un **Workspace**.
2. Entra al detalle de un **Servicio**.
3. Del lado derecho en la sección **Acerca de**, podrás encontrar la url interna para hacer llamados a tu servicio.

<img src={internal} alt="Servicios internos" />

## Usando múltiples despliegues

Dentro de un mismo servicio puedes ejecutar múltiples despliegues de la misma aplicación usando distintas compilaciones, versiones, canales o variables de entorno, puedes configurar como distribuir el tráfico entre estos distintos depliegues en la sección **Balanceo interno** en el detalle de un **Servicio**, configurando las reglas de ruteo como se describe en [Balanceador de carga](/docs/workspaces/lb#configurar-reglas-de-ruteo), aunque en este caso el balanceo será interno y gestionado por un servicio virtual, en lugar de un *LB*.
