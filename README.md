# Azure_SQLServer Guía

Esta guía te acompañará a través de los siguientes pasos para trabajar con Azure y Microsoft SQL Server:

## Contenido

- [Creación de una base de datos SQL Server en Microsoft Azure](#creación-de-una-base-de-datos-SQL-Server-en-microsoft-azure)
- [Establecimiento de una conexión con SQL Server Management Studio](#establecimiento-de-una-conexión-con-sql-server-management-studio)
- [Conexión a la base de datos usando el lenguaje de programación Java](#conexión-a-la-base-de-datos-usando-el-lenguaje-de-programación-java)
- [Conexión a la base de datos usando el lenguaje de programación C#](#conexión-a-la-base-de-datos-usando-el-lenguaje-de-programación-c)

## Primeros pasos

1. Comienza ingresando al [Portal de Azure](https://portal.azure.com/). Esta URL es esencial, ya que te permitirá administrar los servicios de Azure.

2. Utiliza las credenciales de tu cuenta de organización, educación o personal que cuente con una suscripción en Azure.

3. Una vez en tu cuenta, te encontrarás en la pantalla de inicio del Portal de Azure.

   ![Portal de Azure](/img/image.png "Portal de Azure")

# Crear un grupo de recursos

Antes de comenzar, es recomendable crear un grupo de recursos. Este es un contenedor que almacena los recursos relacionados con una solución en Azure.

1. En la barra de búsqueda, busca **Grupos de recursos**.

   ![Buscar grupo de recursos](/img/image-2.png)

2. Verás una lista de los grupos de recursos actuales o creados anteriormente.

   ![Grupo de recursos](/img/image-1.png)

3. Haz clic en el botón de crear y configura los siguientes parámetros:

   ## Detalles del proyecto

   - **Suscripción**: Selecciona la suscripción activa de Azure. **En nuestro caso, elegimos *"Azure for Students"***.

   - **Grupo de recursos**: Proporciona un nombre que siga los requisitos de Azure. Puede ser un nombre clave para tu proyecto o una nomenclatura coherente. **En este caso, será *"Prueba-SQLServer"***.

   ## Detalles del recurso

   - **Región**: Elige una región cercana geográficamente. Puedes consultar las opciones en el [Mapa interactivo](https://datacenters.microsoft.com/globe/explore). **En nuestro caso, elegimos *"South Central US"***.
    ###

   ![Parametros de grupo de recursos](/img/image4.png)

4. Haz clic en Revisar y crear. Verifica que todos los detalles sean correctos y, finalmente, haz clic en Crear. Recibirás una notificación.

5. Una vez creado el grupo de recursos, podrás verlo en la página de Grupos de recursos.

> **Notificaciones:** Azure te notificará sobre eventos como crear, eliminar, actualizar o apagar mediante notificaciones.

# Creación de una base de datos SQL Server en Microsoft Azure

Para crear una base de datos SQL Server en Microsoft Azure, sigue estos pasos:

1. En la página de inicio, busca el recurso de base de datos llamado "SQL Database". Puedes hacerlo de las siguientes maneras:

   - Directamente desde la barra de búsqueda en la parte superior.
   - Haciendo clic en el botón de "Crear un recurso" y navegando a **Categorías > Base de datos** para seleccionar **SQL Database**.
   - En el menú de la izquierda, ve a **Todos los servicios > Bases de datos > Azure SQL > SQL Database**.
   

2. Verás una ventana con las bases de datos disponibles o creadas anteriormente.
3. Haz clic en el botón "Crear".
![Crear base de datos SQL Server](/img/image5.png)

4. En la siguiente ventana, denominada "Crear base de datos SQL", encontrarás varias pestañas: *Básico, Redes, Seguridad, Configuración adicional, Etiquetas, Revisar y crear*. A continuación, se explica la configuración de cada una de ellas.
![Crear base de datos SQL](/img/image6.png)

## Pestaña "Básico"

Configura la pestaña "Básico" de la base de datos con los siguientes parámetros:

### Detalles del proyecto

- **Suscripción**: Selecciona la suscripción activa de Azure. **En nuestro caso, elegimos *"Azure for Students"***.
- **Grupo de recursos**: Selecciona el grupo de recursos donde se almacenará la base de datos. **En nuestro caso, hemos elegido el grupo de recursos creado previamente, llamado *"Prueba-SQLServer"***.

### Detalles de la base de datos

- **Nombre de la base de datos**: Introducimos el nombre de nuestra base de datos. ¨**En nuestro caso, elegimos *Prueba-SQL-Server***
- **Servidor**: Daremos click en el botón de [Crear nuevo](##Creacion-un-servidor-de-SQL-Database) *<-- Haz click en el enlace*
![Crear Nuevo](/img/image7.png)
> Al crear el servidor de SQL Database en la parte superior derecha se mostrara un panel denominado **Resumen del costo**, el cual nos ayudara a visualizar los costos aproximados del recurso. *No se asusten por el costo elevado por mes* 🫠, *este cambiara conforme a la configuracion acontinuacion* 🙂. 
![Resumen de costo](/img/image13.png)
- **¿Quiere usar un grupo elástico de SQL?**: *Seleccionamos **No***
- **Entorno de carga de trabajo**: *Seleccionamos **Implementacion***. *Gracias a esta opcion bajara significativamente el costo aproximado del recurso*
- **Proceso y almacenamiento**

### Redundancia del almacenamiento de copias de seguridad

- **Redundancia de almacenamiento de copia de seguridad**

## Creacion un servidor de SQL Database

Al hacer click en el botón ***Crear nuevo*** nos enviara a una ventana denominada *"Crear un servidor de SQL Database¨*. A continuación, se explica la configuración.

### Detalles del servidor

- **Nombre del servidor**: Proporciona un nombre que siga los requisitos de Azure. **En nuestro caso, elegimos *"pruebasqlserver"***.
- **Ubicacion**: Selecciona una region. *Te recomendamos la region que escogiste en tu grupo de recursos*. **En nuestro caso, elegimos *"South Central US"***.


### Autenticacion
Nos aparece las diferentes maneras de autenticacion para acceder al servidor como:
- **Usar tus credenciales de Azure AD.**: Nos pedira ***Establecer administrador de Azure AD*** el cual deberemos seleccionar dando click en el enlace ***Establecer administrador***. A continuacion, se explica como establecer un administrador de Azure AD.

    1. Se abrira una pequeño panel denominado **Azure Active Directory**. Donde son todos los usuarios de Azure Active Directory de nuestra organizacion
        ![Azure AD](/img/image8.png)  
    2. Buscaremos nuestro administrador en la barra de busqueda mediante su **nombre ó direccion de correo electronico**.
    3. Una vez encontrado nuestro administrador correcto, dar click en la casilla de selecionar. *Este aparecera en el apartado de la derecha*. **En esta caso seleccionamos *Marcos Israel Falcon Alejandre***
    4. Dar click en el boton **Seleccionar**.  
        ![Administrador de AD](/img/image9.png) 
    5. Se vizualizara de la siguiente manera  
    ![Usuario AD](/img/image10.png)

<br></br>

- **Usar la autencacion de SQL.**: Nos solicitara ingresar un nombre de **usuario** y una **contraseña**.

    - **Inicio de sesión del administrador del servidor**: Escribir el nombre de usuario. Siguiendo los requisitos de Azure. **En esta caso, seleccionamos *MarcosFalcon***
    - **Contraseña**: Ingresa una contraseña [Segura](https://www.stackscale.com/es/blog/buenas-practicas-contrasenas-seguras/) y confirmala nuevamente 🙂
![AUTHSQL](/img/image11.png)  

<br></br>

- **Ambas.**: Te permitira Autenticarte mediante tu **usuario de Azure AD** ó **atenticacion de SQL**. Los pasos son iguales a los explicados con anterioridad. *Te recomendamos esta opcion.*  
![Ambos](/img/image12.png)  

> Al finalizar dar click al boton de **"Aceptar"**





