# Kavak Alerts Bot

Este proyecto permite configurar alertas personalizadas en Kavak utilizando **Cloudflare Workers** y **Telegram Bot**.

![Ejemplo de respuesta del bot](https://pbs.twimg.com/media/GHHMsRNaIAAayC5?format=jpg&name=small)

## Requisitos

- Una cuenta en [Cloudflare](https://www.cloudflare.com/)
- [Telegram](https://telegram.org/) con una cuenta activa

## Configuración

### Paso 1: Crear un Worker en Cloudflare

1. Regístrate en Cloudflare en [cloudflare.com](https://www.cloudflare.com/).
2. Ve a la sección de **Workers** y selecciona **Crear aplicación**.
3. Nombra la aplicación como quieras (por ejemplo, `kavak`) y selecciona **Deploy**.

![Crear aplicación en Cloudflare](https://pbs.twimg.com/media/GHHMtKZbcAAWQmX.jpg)
![Crear aplicación en Cloudflare 2](https://pbs.twimg.com/media/GHHMuYIbsAAo6bh.jpg)

4. Una vez que llegues al editor de código, elimina todo el contenido existente y pega el código del siguiente repositorio:

   [Código en GitHub](https://github.com/ferminrp/kavak-alerts-bot/blob/main/worker.js)

### Paso 2: Obtener la URL de Kavak

1. Abre Kavak y aplica los filtros de búsqueda que desees.
2. Haz clic derecho en la página y selecciona **Inspeccionar**.
3. Ve a la pestaña **Network** y dentro de ella selecciona **Fetch/XHR**.
4. Actualiza la página y selecciona la segunda/tercera solicitud que aparece. También puedes filtrar por 'advanced-search?'
5. En la pestaña **Response** verás del archivo JSON de los autos.
6. Copia el **link address**


![Obtener link de búsqueda en Kavak](https://pbs.twimg.com/media/GHHMxsgbkAA1THG?format=jpg)
![Obtener link de búsqueda en Kavak2](https://pbs.twimg.com/media/GHHMyMcbYAAsSc6?format=png)



6. Pega este enlace en la primera línea del código dentro del worker de Cloudflare.

### Paso 3: Configurar Telegram Bot

1. Abre Telegram y busca al usuario `@BotFather`.
2. Usa los comandos de BotFather para crear un nuevo bot.
3. Copia el **token** que te proporciona BotFather.
   
   ![Token en Telegram](https://pbs.twimg.com/media/GHHMzjXbQAA3xcJ?format=png)

4. Pega el token en la segunda línea del código del worker.

### Paso 4: Obtener el Chat ID de Telegram

1. Envia un mensaje al bot que acabas de crear.
2. Accede a la siguiente URL para obtener el `chat_id`: https://api.telegram.org/botAQUITOKENDETUBOT/getUpdates
3. Debes modificar AQUITOKENDETUBOT por el que teha dado @BotFather
4. Pega el `chat_id` que ves allí en el código del worker (3er parametro) .

   ![Chat id](https://pbs.twimg.com/media/GHHM0_VagAAtIGY?format=png)

### Paso 5: Configurar el Trigger

1. Dentro de Cloudflare, ve a la configuración de **Triggers**.
2. Añade un **Cron Trigger** si deseas ajustar la frecuencia de las alertas.

  ![Trigger](https://pbs.twimg.com/media/GHHM2KZbMAAGQJY?format=jpg) 

### ¡Listo!

Con esto, deberías empezar a recibir mensajes en Telegram con la cantidad de autos que coinciden con tus filtros. Si deseas modificar los filtros, solo actualiza la URL en la primera línea del código.

![Ejemplo de respuesta del bot](https://pbs.twimg.com/media/GHHMsRNaIAAayC5?format=jpg&name=small)

---

## Contribuir

Este proyecto es de código abierto y puedes contribuir a través del repositorio en GitHub: [Kavak Alerts Bot](https://github.com/ferminrp/kavak-alerts-bot).

## Licencia

Si queres mejorar el bot podes mandar PR tranquilo o cargar un issue.





## Las instrucciones originales para implementarlo estan en [este tweet](https://x.com/ferminrp/status/1761413996727685442?s=20).



