# Proyecto Arquitectura de Software 2020-2

## Autores:
- David Andrés Herrera Moya
- Jose Luis Gómez Camacho
- Cesar David Villamil Ramos


## Social Academy 📲📚


Social Academy es una red social en donde puedes conectar con tus mejores para generar temas de interés, debatir sobre las tendencias del mercado y mucho más!, además un lugar para divertirse y a la vez estar en la mira del ambiente laboral, y tu estas preparado para conseguir trabajo de una forma diferente.

[![Deployed to Heroku](https://www.herokucdn.com/deploy/button.png)](https://social-academic-2020.herokuapp.com/)

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://socialacademy.azurewebsites.net)


## Manual de uso de la aplicación 📜 

>En la pantalla principal hay dos opciones, la primera es para iniciar sesión, la segunda para registrarse.
Para registrarse de click en el botón de registrar, luego de esto le va a pedir unas opciones como: Nombre, Apellido, correo, entre otras, debe llenar todos los campos y luego de llenar los campos de click en registrar.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/registro.png)

>Una vez este registrado de click en la opción de ingresar, en esta opción aparecerán dos campos por llenar uno es el de correo y el otro es el de la contraseña. Una vez llene estos datos de click en el botón de Login Now y este lo va a direccionar a su muro.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/login.png)

> Una vez usted inicie sesión aparecerá el muro de su biografía, en este usted vera su información y publicaciones.

> Adicionalmente puede realizar publicaciones a su biografía simplemente dando click en el botón publicar luego de escribir algún texto que quiere compartir con sus amigos.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/timeline.png)

> En la parte superior al lado de la foto, usted encontrara un panel con distintas opciones estas opciones lo llevaran a otros lugares de la aplicación dependiendo a cuál quiera ir. 
Además en la parte superior también va a tener distintas opciones como principal, biografía, chats y cerrar sesión.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/timeline_opciones.png)

> Si da click en la parte de información encontrará como primera opción la información básica, esta información usted la puede modificar y hay distintos campos como nombre, país, fecha de nacimiento, entre otras. Después de llenar los datos podrá guardar los cambios en el botón de guardar.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/informacion_basica.png)


> Si le da click en el botón de mensajes este lo redireccionara a una pantalla donde va a poder seleccionar sus amigos y los chats que tiene con el amigo seleccionado

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/amigos.png)

>Esta es la ventana de chat, acá podrá abrir los chats con sus amigos y darles a las diferentes opciones en el panel lateral, como los chats, los amigos y su perfil

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/chats.png)

> En esta vista podrá ver cuáles son sus amigos y podrá darle click en abrir su chat con cada usuario.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/amigos_chat.png)

> En la parte superior derecha encontrara la opción de cerrar sesión.

> ![](https://github.com/cvillamiljr/GitBook/blob/master/images/logout.png)

## Requerimientos no funcionales 🛠

### 1 . Usabilidad

Se hicieron pruebas de usabilidad con un framework llamada CrazyEgg que nos ayuda a monitorear el uso de la aplicación con métricas como los clicks que los usuarios dan a la página, mapas de calor para saber cuáles son las partes de la página en las que más interactúan los usuarios, cuantos usuarios han visitado la página y el total de visitas que se han realizado.

A continuación, se puede observar el mapa de calor de las opciones de registrar usuario y el login:

![](https://github.com/cvillamiljr/GitBook/blob/master/images/heatmap.png)

Como se puede observar en la imagen están incluidas las métricas mencionadas anteriormente y adicionalmente en la parte derecha de la imagen se pueden encontrar otras un poco más detalladas.


### 2 . Escalabilidad

Se hicieron pruebas de carga una vez desplegada la aplicación en el servicio de despliegue de aplicaciones web de azure (Azure App Service).

En primera instancia se realizaron las pruebas con las configuraciones que vienen por defecto en el App Service Plan esto quiere decir con una sola instancia del servidor y el monitor nos arrojó los siguientes resultados.

![](https://github.com/cvillamiljr/GitBook/blob/master/images/CPU%25-1137-1Nodo.png)

El uso de la CPU usando un nodo es de aproximadamente un 53% realizando dos mil peticiones como se muestra en la siguiente imagen.

![](https://github.com/cvillamiljr/GitBook/blob/master/images/RQ-1145-1Nodo.png)

Finalmente se escaló el App service plan para que use 3 instancias de servidor, se hicieron las pruebas con las mismas dos mil peticiones y los resultados fueron los siguientes:

![](https://github.com/cvillamiljr/GitBook/blob/master/images/CPU%25-1145-3Nodo.png)

Lo cual podríamos inferir que al usar prácticamente toda la capacidad de procesamiento de dos de los servidores realizó las dos mil peticiones mucho más rápido como se puede observar a continuación.

![](https://github.com/cvillamiljr/GitBook/blob/master/images/pruebas_3nodos.png)

En comparación con el desempeñó que tuvo al momento de realizar las dos mil peticiones con 1 nodo.

![](https://github.com/cvillamiljr/GitBook/blob/master/images/pruebas_1nodo.png)
