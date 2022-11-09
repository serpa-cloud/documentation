# Cuentas Cloud

Serpa esta orientado a la administración **Multi Cloud**, puedes asociar múltiples cuentas del mismo o distintos proveedores a la [organización](./organizations) en la que estes colaborando.

## Proveedores disponibles

Por el momento, Serpa se puede conectar con **Amazon Web Services (AWS)** y **Google Cloud Platform (GCP)**. En el roadmap de la plataforma está **Microsoft Azure** y **Digital Ocean**.

## Conectando una cuenta Cloud

1. Abre la consola de [Serpa Cloud](https://beta.serpa.cloud/dashboard).
2. Asegurate de estar colaborando en la organización que deseas.
3. Haz click en el menú del lado izquierdo [Clouds](https://beta.serpa.cloud/dashboard/infrastructure/cloud-accounts).
4. Haz click en el botón del lado derecho [Conecta un cloud](https://beta.serpa.cloud/dashboard/infrastructure/cloud-accounts/create).

### Conecta una cuenta de Google Cloud Platform

1. Selecciona el logo de **Google Cloud**.
2. Ingresa el ID de tu proyecto en **Google Cloud**.
3. (Opcional) Crea una [Cuenta de Servicio](https://cloud.google.com/iam/docs/creating-managing-service-accounts) en **Google Cloud**.
4. Crea una [Clave de cuenta de servico](https://cloud.google.com/iam/docs/creating-managing-service-account-keys) en **Google Cloud**.
5. Una vez descargada la Clave de Cuenta de Servicio, en el formulario de Serpa selecciona el archivo que acabas de descargar.
6. Da click en **Conectar con Google Cloud**.

### Conecta una cuenta de Google Cloud Platform

1. Selecciona el logo de **AWS**.
2. Ingresa el ID de tu proyecto en **AWS**.
3. Crea una [Usuario IAM con acceso programatico](https://cloud.google.com/iam/docs/creating-managing-service-account-keys) en **AWS**.
4. Cuando crees el usuario copia el `Access key ID` y el `Secret access key`, después ingresalos en la consola de Serpa.
5. De ser necesario, guarda estas credenciales en un lugar seguro ya que posteriormente no tendrás acceso a ellas.
6. Da click en **Conectar con Google AWS**.
