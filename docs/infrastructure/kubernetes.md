# Clústeres de Kubernetes

Serpa corre tus apps (microservicios, servidores y aplicaciones dinámicas) en **Clústeres de Kubernetes (k8s)**, por lo que es necesario contar con recursos de Kubernetes asociados en tu organización de Serpa, para hacerlo cuentas con dos opciones.

* Crear un clúster de Kubernetes nuevo. (Opción recomendada)
* Agregar un clúster de Kubernetes existente.

:::info

Para asociar o crear un clúster es necesario, haber [Conectado una cuenta Cloud](/docs/cloud-accounts)

:::

## Crear un cluster

1. En el menú principal da click en [Clústeres de Kubernetes](https://beta.serpa.cloud/dashboard/infrastructure/compute).
2. Da click en el botón **Agregar Clúster** y en el modal selecciona [Crear nuevo clúster](https://beta.serpa.cloud/dashboard/infrastructure/compute/create).
3. Selecciona la cuenta Cloud donde vás a desplegar.

### Crear un clúster en AWS

4. Selecciona la región donde quieres crear el recurso. Te recomendamos buscar la región mas cercana a tus usuarios.
5. Da click en **Continuar**.
6. Selecciona un nombre para tu clúster.
7. Selecciona el tipo de instancia.
8. Define el tamaño deseado, mínimo y máximo de tu clúster.
9. Da click en **Crear clúster**.

### Crear un clúster en Google Cloud

4. Selecciona si el despliegue de tu clúster sera **Regional** o **Zonal**, cuando seleccionas Regional, se replicara el número de nodos (instancias) que definas en cada zona de la región (la mayoría de las regiones tienen 3 zonas).
   - Ejemplo: Si defines un tamaño de tres nodos en **us-central1**, se crearán 3 nodos en  *us-central1-a*, 3 nodos en *us-central1-b* y 3 nodos en *us-central1-c*, dando como resultado 9 nodos en total.
5. Selecciona la región o la zona deseada.
6. Da click en **Continuar**.
7. Selecciona un nombre para tu clúster.
8. Selecciona el tipo de instancia.
9. Define el tamaño deseado.
10. Da click en **Crear clúster**.

Despúes de empezar a **Crear un clúster** el recurso se empezara a crear (tardara de 10 a 15 min), podrás ver el status y el listado de recursos en la sección [Clústeres de Kubernetes](https://beta.serpa.cloud/dashboard/infrastructure/compute).

## Asociar un clúster

:::caution

Es recomendable usar un Clúster nuevo creado con Serpa, si quieres usar un Clúster pre existente en tu cuenta Cloud, es necesario instalar [Istio](https://istio.io/) y para AWS también es necesario instalar [AWS Load Balancer Controller](https://github.com/kubernetes-sigs/aws-load-balancer-controller)

:::

1. En el menú principal da click en [Clústeres de Kubernetes](https://beta.serpa.cloud/dashboard/infrastructure/compute).
2. Da click en el botón **Agregar Clúster** y en el modal selecciona [Conectar clúster existente](https://beta.serpa.cloud/dashboard/infrastructure/compute/connect).
3. Selecciona la cuenta Cloud donde vás a desplegar.

### Asociar un clúster en AWS

4. Selecciona la región donde se ubica el recurso.
5. Da click en **Buscar clústers**.
6. Selecciona el recurso que quieres asociar.
7. Da click en **Guardar clúster**.

### Asociar un clúster en Google Cloud

4. Selecciona si el clúster es regional o zonal.
5. Selecciona la región o zona donde se ubica el recurso.
6. Da click en **Buscar clústers**.
7. Selecciona el recurso que quieres asociar.
8. Da click en **Guardar clúster**.

Después de **Guardar el clúster**, este ya estara asociado a Serpa. Para poder usarlo, asegurate de tener instalado en el clúster [Istio](https://istio.io/) y en caso de usar AWS, [AWS Load Balancer Controller](https://github.com/kubernetes-sigs/aws-load-balancer-controller).
