import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

import lb from './lb.png';
import mapping from './mapping.png';
import pathAll from './pathAll.png';
import pathEqual from './pathEqual.png';
import authEqual from './authEqual.png';
import pathPrefix from './pathPrefix.png';

# Balanceador de carga (exponer un servicio)

Para poder exponer uno o varios servicios a internet, es necesario configurar reglas de ruteo en un balanceador de carga. Por defecto Serpa usa balanceadores Ingress, para AWS son [ALB - Application Load balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html), para GCP son [Balanceadores de cargas de HTTP(S) de Google Cloud](https://cloud.google.com/kubernetes-engine/docs/concepts/ingress?hl=es-419).

<img src={lb} alt="Balanceadores de carga" />

## Configurar reglas de ruteo

Para configurar reglas de ruteo:

<img src={mapping} alt="Balanceadores de carga" />

1. Entra a la sección **Balanceador de carga** en el detalle de un **Workspace**.
2. Da click en **Editar mapeo** para entrar al modo de edición.
3. Para agregar una nueva regla, haz click en el botón **Agregar mapeo** de la barra en el fondo de la pantalla
4. Del lado izquiero da click en **Agregar condiciones**:
   * En el panel que se abre del lado derecho, haz click en **Agregar condicion**.
   * Para que la petición sea aceptada, debe cumplir todas las condiciones que agregues en este panel.
   * Define que parametro vas a evaluar en la condición, puedes revisar más [información](/docs/workspaces/lb#parametrós-en-las-condiciones)
   * Define que tipo de evaluación vas a realizar:
     * **Exact**: la coincidencia debe ser exacta.
     * **Prefix**: Todo lo que comience con.
     * **Regular expresion**: Lo que cumpla con una expresión regular dada.
   * Define el valor que debe tener tu parametro.
   * Da click en **Guardar**
5. Del lado izquiero da click en **Agregar destinos**:
   * En el panel que se abre del lado derecho, haz click en **Agregar destino**.
   * En el dropdown selecciona el despliegue que recibirá el tráfico que cumpla las condiciones antes definidas.
   * Introuce el porcentaje de tráfico que atenderá el despliegue.
   * Puedes definir varios destinos, siempre y cuando sus porcentajes sumen el 100%
6. Usando las flechas que están a la izquierda de cada mapeo, puedes ordenar que condiciones se deben cumplir primero, en caso de que una petición sea valida, está ya no será procesada por condiciones posteriores.

### Parametrós en las condiciones:

<Tabs>
  <TabItem value="path" label="Path" default>
    El parametró <strong>Path</strong> evalua la ruta después del dominio, por ejemplo:<br /><br />

   
    // Para la URL
    https://www.somethingcool.com/api/v2/users

    // El path sería
    /api/v2/users
    
  </TabItem>
  <TabItem value="scheme" label="Scheme">
    El parametró <strong>Scheme</strong> evalua el protocolo o esquema de la petición (<a href="https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml" target="_blank">Más información sobre schemas</a>):<br /><br />


    // Para la URL
    https://www.somethingcool.com/api/v2/users

    // El scheme sería
    https
  </TabItem>
  <TabItem value="method" label="Method">
    El parametró <strong>Method</strong> evalua el método en la petición (<a href="https://developer.mozilla.org/es/docs/Web/HTTP/Methods" target="_blank">Más información sobre Métodos de petición HTTP</a>):<br /><br />


    // Ejemplos

    GET, POST. PUT, DELETE, PATCH, OPTIONS
  </TabItem>

  <TabItem value="authority" label="Authority">
    El parametró <strong>Authority</strong> evalua el dominio o ip más el puerto de la petición explicitamente definido (<a href="https://stackoverflow.com/a/20950626" target="_blank">Más información sobre Authority</a>):<br /><br />


    // Para la url
    http://www.example.com/

    // El Authority sería
    www.example.com

    // Para la url
    https://www.example.com/somepath

    // El Authority sería
    www.example.com

    // Para la url
    http://www.example.com:8080/somepath

    // El Authority sería
    www.example.com:8080

    // Para la url
    http://255.255.255.255:8080/

    // El Authority sería
    255.255.255.255:8080
  </TabItem>

  <TabItem value="header" label="Header">
    El parametró <strong>Header</strong> evalua un encabezado de la petición (<a href="https://developer.mozilla.org/es/docs/Web/HTTP/Headers" target="_blank">Más información sobre Headers</a>):
    <br />
    <br />
    Cuando evaluas un <strong>Header</strong> tienes que definir el nombre del encabezado a evaluar en el campo <strong>Nombre de parametró</strong>, escrito en minúsculas.
    <br />
    <br />


    // Para evaluar el header Content-type
    Parameter name = content-type
  </TabItem>

  <TabItem value="query" label="Query string">
    El parametró <strong>Query parameter</strong> evalua un parametró de busqueda de la querystring de una url (<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams" target="_blank">Más información sobre URLSearchParams</a>):
    <br />
    <br />
    Cuando evaluas un <strong>parametro Query string</strong> tienes que definir el nombre del URLSearch Param a evaluar en el campo <strong>Nombre de parametró</strong>, escrito en minúsculas.
    <br />
    <br />


    // Para la url
    http://example.com/search?query=pelota&limit=25
    
    // Puedes evaluar el parametro query
    Parameter name = query
    // Su valor sería
    pelota
  </TabItem>
</Tabs>

### Ejemplos de condiciones

En el siguiente ejemplo, esta condición va a cumplirse con todas las peticiones cuyo path sea exactamente igual a ```/_graphql```:

```
https://www.somethingcool.com/_graphql
https://mycrazyhost.com/_graphql
```
<img src={pathEqual} alt="Reglas del balanceador de carga sobre ruta" />

En el siguiente ejemplo, esta condición va a cumplirse con todas las peticiones cuyo dominio más puerto explicitamente definido sea exactamente igual a ```static.yellowcode.io```:

```
https://static.yellowcode.io/some-path
http://static.yellowcode.io/my-profile
```
<img src={authEqual} alt="Validación Authorithy en Balanceador de carga" />

En el siguiente ejemplo, esta condición va a cumplirse con todas las peticiones cuyo path sea empiece con ```/media/upload```:

```
https://www.somethingcool.com/media/upload
https://mycrazyhost.com/media/upload/my-custom-id/metadata
```
<img src={pathPrefix} alt="Validación Path en Balanceador de carga" />

En el siguiente ejemplo, esta condición va a cumplirse con todas las peticiones:

<img src={pathAll} alt="Validación Path en Balanceador de carga" />
