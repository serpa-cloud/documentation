import deployments from './deployments.png';

# Despliegues

Cuando creas un despliegue es cuando una instancia de tu **app** se empieza a ejecutar, una **app** siempre se ejecuta en el contexto de un servicio en un workspace.

<img src={deployments} alt="Despliegues" />

## Crear un despliegue

1. Accede a la sección **Servicios** en el detalle de un **Workspace**.
2. Entra al detalle de un **Servicio**.
3. Da click en el botón **Crear un despliegue**.
4. Ingresa un nombre y una descripción corta.
5. Selecciona un origen para tu despliegue:
   * **Artefacto**: Da click en el dropdown *Origen* y selecciona de la lista de [compilaciones](/docs/apps/builds) disponibles en tu *app*.
   * **Release**: Da click en el dropdown *Origen* y selecciona de la lista de [versiones](/docs/apps/versions) disponibles en tu *app*.
   * **Release Channel**: Da click en el dropdown *Origen* y selecciona de la lista de [canales de actualización](/docs/apps/release-channels) disponibles en tu *app*. Cuando seleccionas esta opción el despliegue se irá actualizando automaticamente conforme haya cambios en tu repositorio.
6. Agrega variables de entorno que se aplicarán solo a este despliegue. Para más información visita [Precedencia de variables de entorno y sobreescritura](/docs/others/env-vars).
7. Da click en en **Guardar**.
