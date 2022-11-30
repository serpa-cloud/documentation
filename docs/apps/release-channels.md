import channels from './release-channels.png';

# Canales de actualización

Los **Canales de Actualización** son flujos de **Continous deployment** que permiten suscribir aplicaciones que se están ejecutando a cambios en tu repositorio de Git, puedes suscribir multiples despliegues a un mismo canal, y puedes crear tantos canales como quieras.

<img src={channels} alt="Canales de actualización" />

Para crear un Canal de actualización, en la sección **Canales de actualización** del detalle de una app:

1. Da click en el botón **Crear un canal de versiones**.
2. Ingresa un nombre y una descripción, que te ayuden a identificar este **_canal_**.
3. Selecciona una fase de desarrollo, que identifique la estabilidad de los cambios publicados.
4. Selecciona si quieres compilar a partir de los cambios en un branch o una rama.
5. Escribe el nombre del branch/tag o una expresión regular para evaluar contra el nombre del branch/tag, ejemplo la siguiente expresion va a ejecutar cambios en cualquier branch o tag.

```js
/.*/
```

Para ejecutar cambios en tags o branches de la forma *v2.34.2* podrías usar

```js
/^v\d+\.\d+\.\d+$/
```

6. En el selector **Imágen inicial** selecciona una compilación con la que se inicializará el **Canal de actualizaciones**, ya que no puede haber canales sin versiones a las cuáles suscribirse.

7. Agrega **Variables de entorno** que se usarán solo en los despliegues que consuman este **Canal de actualizaciones** (Opcional). Para más información visita [Precedencia de variables de entorno y sobreescritura](/docs/others/env-vars).

8. Da click en el botón **Guardar**.
