# Proyecto IDP Request Tracker #
Comenzamos con la instalación de los paquetes necesarios para RT

![](images/Captura1.PNG)

El paquete libapache2-mod-fastcgi ya no tiene repositorio asi que tendremos que descargarlo eh instalarlo manualmente

![](images/Captura2.PNG)

![](images/Captura3.PNG)

Una ves intalado este paquete tendremos que quitarlo el comando que ejecutamos y volver a ejecutarlo para instalar los demas, ademas tendremos que darle a si cuando se nos pregunte si queremos instalar los paquetes.

Continuamos con la instalación y nos salta la primera ventana de configuración en la que tendremos que reemplazar lo que nos salga por **netmgmt**.

![](images/Captura4.PNG)

A continuación nos preguntara si queremos configurar la base de datos para request-tracker4 con dbconfig-common a ñp que le daremos que si

![](images/Captura5.PNG)

A continuación nos pide crear una contraseña para la base de datos le damos a que si y ponemos la que queramos

![](images/Captura6.PNG)

![](images/Captura7.PNG)

y confirmamos contraseña

![](images/Captura8.PNG)

A continuación tendremos que crear una contraseña para el usuario root que sera con el que accederemos posteriormente a la herramienta

![](images/Captura9.PNG)

confirmamos contraseña

![](images/Captura10.PNG)

Tendremos que darle contraseña al usuario root de la base de datos, se aconseja dar la misma contraseña para no liarnos

![](images/Captura11.PNG)

ponemos la contraseña y la confirmamos

![](images/Captura12.PNG)

Iremos a este directorio, crearemos un nuevo archivo de configuración llamado 90-local

![](images/Captura13.PNG)

Agregue las siguientes dos líneas al archivo 90-local

![](images/Captura14.PNG)

En la entrada de la Lista de referencia de referencia xxxx es la dirección IP de su PC y SERVNAME es el nombre de su PC.
Asegúrese de usar la dirección IP y el nombre correctos para su PC, luego guarde el archivo y ejecute el comando:

- $ sudo update-rt-siteconfig

Por ultimo tenemos que hacer unos ultimos cambios sobre el servidor web apache:
- $ cd /etc/apache2/conf-available
- $ sudo ln -s /etc/request-tracker4/apache2-modperl2.conf rt4.conf
- $ sudo a2enconf rt4 
- $ sudo service apache2 restart

Inicie sesión en RT como usuario root via web:

![](images/Captura15.PNG)

A continuación mostrare pestañas y rutas donde podemos configurar las siguientes cosas:


- **CREAR USUARIO: Herramientas => Configuración => Usuarios**

![](images/Captura16.PNG)

![](images/Captura17.PNG)

- **CREAR GRUPO DE USUARIO: Herramientas => Configuración => Grupo => Crear**

![](images/Captura18.PNG)

![](images/Captura19.PNG)

- **AGREGAR UN USUARIO A UN GRUPO**

![](images/Captura20.PNG)

![](images/Captura21.PNG)

- **CREAR COLAS: Herramientas => Configuración => Cola => Crear**

![](images/Captura22.PNG)

![](images/Captura23.PNG)

- **Dar derechos a nuestro grupo en la cola: Herramientas => Configuración => Cola => Seleccionar**

![](images/Captura24.PNG)

![](images/Captura25.PNG)

 
