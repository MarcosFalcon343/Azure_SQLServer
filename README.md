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

## Crear un grupo de recursos

Antes de comenzar, es recomendable crear un grupo de recursos. Este es un contenedor que almacena los recursos relacionados con una solución en Azure.

1. En la barra de búsqueda, busca **Grupos de recursos**.

   ![Buscar grupo de recursos](/img/image-2.png)

2. Verás una lista de los grupos de recursos actuales o creados anteriormente.

   ![Grupo de recursos](/img/image-1.png)

3. Haz clic en el botón de crear y configura los siguientes parámetros:

   ### Detalles del proyecto

   - **Suscripción**: Selecciona la suscripción activa de Azure. **En nuestro caso, elegimos *"Azure for Students"***.

   - **Grupo de recursos**: Proporciona un nombre que siga los requisitos de Azure. Puede ser un nombre clave para tu proyecto o una nomenclatura coherente. **En este caso, será *"Prueba-SQLServer"***.

   ### Detalles del recurso

   - **Región**: Elige una región cercana geográficamente. Puedes consultar las opciones en el [Mapa interactivo](https://datacenters.microsoft.com/globe/explore). **En nuestro caso, elegimos *"South Central US"***.
    ###

   ![Parametros de grupo de recursos](/img/image4.png)

4. Haz clic en Revisar y crear. Verifica que todos los detalles sean correctos y, finalmente, haz clic en Crear. Recibirás una notificación.

5. Una vez creado el grupo de recursos, podrás verlo en la página de Grupos de recursos.

> **Notificaciones:** Azure te notificará sobre eventos como crear, eliminar, actualizar o apagar mediante notificaciones.

