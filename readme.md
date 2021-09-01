**Funcionalidades realizadas:**

Agregar elementos a cualquier categoría (rubro, persona, ubicación y especie)

Agregar productos (Asociados a una categoría)

Buscar productos de una instancia de alguna categoría

Buscar productos dado un numero de identificación o un rango de numeros

**Tecnologías usadas:**

- **Frontend:**
    - HTML
    - BOOTSTRAP: Framework de CSS
    - Javascript: Lenguaje de programación
- **Backend:**
    - Nodejs
        - Express: Modulo para crear el servidor
        - ejs: Motor de plantillas
    - MariaDB: Gestor de base de datos Relacional

**Organización de carpetas del proyecto**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9fca7a23-a047-4a1e-9495-194c3d433d0d/Untitled.png)

**Carpetas:**

- **SQL:** contiene archivo de la base de datos
    - **tablas.sql**: contiene el esquema de las tablas a insertar en el gestor de base de datos
- **src:** contiene todos los archivos del programa
    - **public / js:** archivos javascript públicos
        - **enviarFormulario:** contiene los archivos Javascript necesarios para enviar formularios desde el lado del cliente al servidor
        - **search.js:** archivo javascript de la vista que contiene la funcionalidad **buscar productos por categoria**
        - **searchId.js**: archivo javascript de la vista que contiene la funcionalidad **buscar productos por numero de identificación o rangos**
        - **productos.js:**
        - **searchId.js**: archivo javascript de la vista que contiene la funcionalidad **agregar productos**
    - **routes:** contiene las rutas del backend
        - **addData.js:** contiene todas las rutas que modifiquen datos
        - **getInfo.js:** contiene todas las rutas que muestren información
        - **index.js:** contiene ruta principal
    - **views:** contiene las vistas del lado del cliente (Frontend)
        - **partials:** contiene elementos HTML re-utilizables
            - head.ejs
            - nav.ejs
            - footer.ejs
        - **addEspecie.ejs:** vista que muestra la **funcionalidad agregar Especie**
        - **addPersona.ejs:** vista que muestra la **funcionalidad agregar Persona**
        - **addProducto.ejs:** vista que muestra la **funcionalidad agregar Producto**
        - **addRubro.ejs:** vista que muestra la **funcionalidad agregar Rubro**
        - **addUbicacion.ejs:** vista que muestra la **funcionalidad agregar Ubicación**
        - **index.ejs:** vista que muestra la pantalla principal
        - **search.ejs:** vista que muestra **la funcionalidad buscar productos por categoría**
        - **searchId.ejs:** vista que muestra **la funcionalidad buscar productos por numero de id o rango**
    - **database.js:** archivo encargado de conectarse con la Base de Datos
    - **index.js:** archivo encargado de la configuración y la ejecución del servidor.
    - **key.js:** archivo con las claves de conexión a la base de datos

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1fd24bd0-33fa-4d33-a487-daf434934aaf/Untitled.png)

## Configurar base de datos

En este caso usaré Mariadb

- Descargar desde su pagina oficial
- Al momento de instalarlo se le pedirá una contraseña para el usuario "root"
- Buscar un programa llamado MySQL Client (MariaDB)

    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5eb892a0-d5b4-45d9-be14-6164cb279094/Untitled.jpeg)

    - Ingresar la contraseña, luego aparecerá:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fdac0e8a-2d95-4283-9cf3-75d4c172de4b/Untitled.jpeg)

Aquí debe ingresar los siguientes comandos:

```bash
CREATE DATABASE INSUCO;
USE INSUCO;
```

Debería salir algo así:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f39e7ed6-6870-481f-9cfc-52285edb294f/Untitled.png)

Luego ingresar los datos del archivo tabla.sql de la carpeta SQL

Si no hay errores, eso es lo único que hay que hacer en la base de datos.

## Obtener repositorio e instalar dependencias

Para descargar el proyecto se debe tener instalado NodeJs y Git (buscar en la web)

Una vez descargado e instalado los programas ingresar a la consola o teminal de comandos y clonar el repositorio. usar:

```bash
git clone https://github.com/mgeld542/inventario
```

luego de esto deberá:

- Ingresar a la carpeta inventario
- Instalar paquetes con npm

Para esto debe ejecutar

```bash
cd inventario
npm install
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b411d8ed-5c7c-4896-b78a-fb28ebce45cd/Untitled.png)

Luego debe cambiar los valores del archivo **keys.js**

- en user debe poner **root**
- en password debe poner la contraseña que escogió al momento de instalar la base de datos

Luego debe ingresar en la consola:

```bash
npm run dev
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fba36b6f-ea75-4792-8cbf-245a01c7119c/Untitled.png)

Luego debe ingresar en un navegador a [http://localhost:5001/](http://localhost:5001/) donde le debe salir algo como esto:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1a52d7b8-c9a9-4883-bb91-bc666784af56/Untitled.png)

Cualquier cambio realizado en los archivos debería reflejarse al momento de guardar los cambios, (Gracias al modulo de desarrollo nodemon)
