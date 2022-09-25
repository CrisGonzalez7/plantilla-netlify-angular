# Plantilla de Angular para Netlify
![netlify + angular logo](https://res.cloudinary.com/dzkoxrsdj/image/upload/v1646339469/angular_wzrs5o.png)

Este es un proyecto angular básico que contiene todo lo necesario para implementarlo directamente en [Netlify](https://netlify.com). 

## Índice:

- [Usar este Template](#usar-este-template)
  - [Clonar repositorio](#clonar-repositorio)
  - [Cambiar nombre al proyecto](#cambiar-nombre-al-proyecto)
  - [Subir los cambios](#subir-los-cambios)
- [Netlify CLI](#netlify-cli)
  - [Compartir Proyecto](#compartir-proyecto)
    - [Autorizar con Netlify](#autorizar-con-netlify)
    - [Token en GitHub](#token-en-github)
  - [Publicando el Proyecto](#publicando-el-proyecto)
- [Trabajando con GitHub](#trabajando-con-github)
  - [Mezclando con Main](#mezclando-con-main)
- [Configurando Netlify con GitHub](#configurando-netlify-con-github)
- [FAQs](#faqs)
  - [Repositorio Public y Private](#repositorio-public-y-private)

## Usar este Template

Para usar este Template, haz clic en el boton `Use this Template`

En `Repository name` coloca el nombre de tu proyecto. 

Selecciona si deseas que tu proyecto sea `Public` o `Private` 

> Si no sabes qué opción seleccionar, revisa la sección [Repositorio Public y Private](#repositorio-public-y-private)

Haz clic en `Create repository from template`

### Clonar repositorio

Para clonar tu repositorio y realizar modificaciones desde tu PC, sigue los siguientes pasos:
- Crea una carpeta en tu computador donde almacenarás el proyecto
- Abre la carpeta con [Visual Studio Code](https://code.visualstudio.com)
- Ve al menú superior de Visual Studio Code y abre un terminal
- En el repositorio que haz creado, haz clic en `Code` y copia el link que aparece en `HTTPS`
- Ejecuta el siguiente comando 

```bash
git clone [PEGA AQUÍ EL LINK DE TU REPOSITORIO] 
```

- Luego, entra a la carpeta del proyecto con el comando:

```bash
cd [NOMBRE CARPETA]
```
> El nombre de la carpeta es el mismo nombre que pusiste en el repositorio. 

Para instalar los paquetes necesarios ejecuta el siguiente comando:

```bash
npm install
```

Para verificar que esté todo funcionando de manera correcta, puedes levantar un servidor local con el comando:

```bash
ng serve
```

> Si te lanza el siguiente mensaje `? Port 4200 is already in use. Would you like to use a different port?` pon la letra `Y` y presiona `enter`

Si todo salió correctamente, te debería lanzar el siguiente mensaje `** Angular Live Development Server is listening on localhost:[NUMERO], open your browser on http://localhost:[NUMERO]/ **`

Puedes ingresar directamente al link haciendo clic con la tecla `Ctrl` presionada. 

> Para dejar de ejecutar el servidor presiona `Ctrl` + `C` en la terminal de Visual Studio Code. 

### Cambiar nombre al proyecto

En este momento tu proyecto tiene el nombre `angular-quickstart` por defecto. 

Para ponerle un nombre personalizado, en VSCode presiona `Ctrl` + `Shift` + `F`, esto debería abrirte el buscador

> Si no te funciona, puedes ir directamente a la lupa en el panel izquierdo y esto te abrirá el buscador.

Busca: 

```bash
angular-quickstart
```

Deberían aparecer `22 resultados en 9 archivos`

- En la parte izquierda del buscador aparece una flecha `>`, haz clic ahí y te aparecerá un campo que dice `Reemplazar`. 
- Pon el nombre de tu proyecto en ese campo.
- En la parte derecha del campo, hay un botón que al poner el cursor sobre él dice `Reemplazar todo`
- Haz clic en `Reemplazar todo` y te aparecerá un mensaje que dice `Reemplazar 22 apariciones en 9 archivos por "[NOMBRE INGRESADO]"`
- Haz clic en `Reemplazar`

Para verificar que los cambios se guardaron correctamente `Ctrl` + `Shift` + `G`, esto debería abrirte el panel de Git.

> Si no te funciona, puedes ir directamente a la opción bajo la lupa en el panel izquierdo, la cual se llama `Control de código fuente`.

Y debería aparecer un listado con 9 archivos que han sufrido modificaciones. 

### Subir los cambios

Vamos a actualizar los archivos en GitHub para que contengan el nuevo nombre del proyecto. Para esto vamos a verificar que esté bien linkeado nuestro proyecto con el repositorio de GitHub.

- Ejecuta el siguiente comando: 

```bash
git remote -v
```

Esto debería darte como resultado el link de tu repositorio. 

- Para ver los archivos que han sido modificados ejecuta: 

```bash
git status
```

- Para poder subir los cambios a GitHub ejecuta: 

```bash
git add .
git commit -m "[DESCRIPCION DEL COMMIT]"
```

- Y luego: 

```bash
git push -u origin main
```

> Si deseas verificar que los cambios fueron subidos correctamente, ingresa al link de tu repositorio y debería aparecer el nombre del commit que haz realizado.

¡Ya puedes empezar a trabajar en tu proyecto!

## Netlify CLI

También puedes ejecutar tu proyecto localmente utilizando [Netlify CLI](https://docs.netlify.com/cli/get-started/)

Para iniciar la instalación sigue los siguientes pasos:

- Abre un nuevo terminal haciendo clic en `+` en la sección de la terminal de Visual Studio Code. 

- Luego, entra a la carpeta del proyecto con el comando:

```bash
cd [NOMBRE CARPETA]
```

- En la terminal ejecuta:

```bash
npm install netlify-cli -g
```

> Si eres usuario de Ubuntu, o alguna otra distribución basada en Ubuntu, utiliza este comando: `sudo npm install netlify-cli -g`

- Una vez terminada la instalación, puedes comprobar la versión instalada y encontrar información básica de la herramienta, con el siguiente comando: 

```bash
netlify
```

Para ejecutar tu proyecto de manera local utiliza:

```bash
netlify dev
```

Debería abrirse tu proyecto automáticamente en el navegador.

> Si no se abre de forma automática, puedes ir al mensaje `Server now ready on http://localhost:[NUMERO]` e ingresar al link haciendo clic con la tecla `Ctrl` presionada. 

> Para dejar de ejecutar el servidor presiona `Ctrl` + `C` en la terminal de Visual Studio Code. 

### Compartir Proyecto

Para conectarte con Netlify y poder compartir tu proyecto en la web:

- Abre un nuevo terminal haciendo clic en `+`en la sección de la terminal de Visual Studio Code. 

- Luego, entra a la carpeta del proyecto con el comando:

```bash
cd [NOMBRE CARPETA]
```

- Ejecuta: 

```bash
netlify init
```

Esto te abrirá una pestaña en el navegador donde deberás acceder a tu cuenta de Netlify, o crear una cuenta si no la posees.

Una vez hayas ingresado a Netlify, te llevará a una pantalla donde te pedirá autorizar a la aplicacción Netlify CLI, y te entregará detalles sobre los permisos que le concederás. Básicamente se trata de una autorización para que Netlify CLI pueda crear y administrar sitios en tus equipos de Netlify. Puedes revocar el acceso cuando así lo desees. 

Haces clic en `Authorize`, y te saldrá una pantalla en la cual se confirma que la autorización fue concedida con éxito; ya puedes cerrar esa pestaña del navegador. 

Volviendo a Visual Studio Code te saldrá el siguiente mensaje: 

> You are now logged into your Netlify account!

Y también te preguntará:

> How do you want to link this folder to a site?

Te saldrán dos opciones 

> ⇄  Connect this directory to an existing Netlify site 
> +  Create & configure a new site 
 
- Selecciona `+  Create & configure a new site` utilizando las flechas `subir` y `bajar` de tu teclado y presiona `Enter`

- Luego te aparecerá una linea que dice `Team`, selecciona el equipo que deseas utilizar y presiona `Enter`

Te aparecerá una linea que dice `Site name`, y por defecto te entragará un nombre entre paréntesis, puedes cambiarlo de inmediato borrando la línea e introduciendo el nombre que deseas ponerle a tu sitio. 

> Si te aparece el siguiente mensaje `Warning: [NOMBRE].netlify.app already exists. Please try a different slug.` significa que ya existe en Netlify un proyecto con ese nombre, para poder continuar debes modificar el nombre del proyecto hasta que encuentres uno que esté disponible, o usar el que te entraga por defecto (puedes cambiarlo más adelante).

Si no hay problemas con el nombre elegido, te saldrá un mensaje que dice `Site Created` y te entregará los siguientes detalles: 

`Admin URL`

`URL`

`Site ID`

Puedes hacer clic en el link de `Admin URL` y acceder a las configuraciones de tu sitio. También puedes hacer clic en el link de `URL` y ver el sitio desplegado. 

> No se desplegará tu sitio hasta que ejecutes el siguiente paso:  

Luego te pedirá acceso a tu cuenta de GitHub para configurar Webhooks y Deploy Keys. Puedes autorizar a través de Netlify o con un token de GitHub. Selecciona la opción que mejor te parezca. 

  - [Autorizar con Netlify](#autorizar-con-netlify)
  - [Token en GitHub](#token-en-github)

#### Autorizar con Netlify

- Selecciona `Authorize with GitHub through app.netlify.com`. Esto te abrirá una pestaña en el navegador que dice `Sign in to Netlify CLI`
- En `Connect to Git provider` selecciona GitHub.

Te aparecerá el siguiente mensaje: `Logged In. You're now logged into Netlify CLI with your github credentials. Please close this window.` Ya puedes cerrar esa ventana.

Una vez hayas realizado todos los pasos ve a la sección [Publicando el Proyecto](#publicando-el-proyecto)

#### Token en GitHub

Para poder obtener un Token en [GitHub](https://github.com/), en el menú debes ir a `settings`, luego en las opciones de la columna izquierda haces clic en `Developer Settings`. Después vas a `Personal access tokens` y en la esquina superior derecha haces clic en el botón `Generate new token`. 

En `Note` colocas un nombre que identifique al Token, ejemplo `Token para Netlify`
En `Expiration` te recomiendo dejarlo en `30 days`
En `Select scopes` te recomiendo seleccionar todas las opciones para no tener problemas más adelante

Luego haces clic en el botón `Generate token` 

🚨 Es importante que lo copies y lo utilices de inmediato ya que GitHub no te permite tener acceso nuevamente al token. 

Volviendo al terminal de Visual Studio Code (VSCode), debes pegar el token de Github para continuar.

### Publicando el Proyecto

- En la terminal de VSCode te aparecerá una linea que dice `Your build command`, debes dejarlo por defecto, solo presiona `Enter` 

- Luego te aparece otra linea que dice `Directory to deploy`, debes dejarla por defecto para no tener problemas al desplegar el sitio. 

Si todo ha salido bien te aparecerá un mensaje que dice `Success! Netlify CI/CD Configured!`

Y si ejecutas el comando 

```bash
netlify open
```

Te abre una pestaña en el navegador con la página de administración de tu sitio. 

> Si no se abre de forma automática, puedes ingresar al link haciendo clic con la tecla Ctrl presionada.

## Trabajando con GitHub 

Te recomiendo trabajar en una rama aparte de `main`.

- Para crear una rama ejecuta: 

```bash
git branch [NOMBRE DE LA RAMA]
```

> Generalmente en mis proyectos personales creo una rama llamada `rama` y así no me complico la vida ;)

- Para cambiar a la rama creada ejecuta:

```bash
git checkout [NOMBRE DE LA RAMA]
```

Haz los cambios que desees en tu proyecto.

Para ver los archivos que han sido modificados ejecuta: 

```bash
git status
```

Para poder subir los cambios a GitHub ejecuta: 

```bash
git add .
git commit -m "[DESCRIPCION DEL COMMIT]"
```

Y luego: 

```bash
git push -u origin [NOMBRE DE LA RAMA]
```

### Mezclando con Main 

Para mezclar la rama creada con la rama main (que es la principal), debes ir al link de tu repositorio en [GitHub](https://github.com/)

> Si lo olvidaste el link de tu repositorio puedes acceder a él con el comando `git remote -v`

- Una vez en GitHub, es probable que te aparezca un mensaje como este ` [NOMBRE DE LA RAMA] had recent pushes [TIEMPO] ago`, y al lado un botón que diga `Compare & pull request`

> Si no te sale ese mensaje puedes hacer clic en `main` luego ir a la rama en cuestión y en `contribute` hacer clic en `Open Pull Request`

En Write puedes escribir una descripción de tu proyecto (si quieres) y presionar `Create pull request`

Luego, si te dice `This branch has no conflicts with the base branch` significa que está todo correcto y al hacer clic en `Merge pull request` y luego en `Confirm merge` los cambios serán enviados a la rama `main`

Puedes ir a la pestaña `Code` para ver los cambios

## Configurando Netlify con GitHub

En este momento tu proyecto en Netlify está linkeado con tu repositorio en GitHub. Para comprobar esto ejecuta: 

```bash
netlify open
```

Esto te abrirá una pestaña en el navegador con la página de administración de tu sitio. 

- Debajo del link de tu web haz clic en `GitHub`, esto te abrirá el repositorio al cual está linkeado.

Por último, haz clic en el link de tu sitio para verificar que se haya desplegado de forma correcta.

Desde este momento, cada vez que actualices la rama `Main`, los cambios se verán reflejados en Netifly de forma automática. 

## FAQs

### Repositorio Public y Private

*¿Cuál es la diferencia entre un repositorio público y uno privado?*

Básicamente, un repositorio público es visible a todo el público, es decir, tu código puede ser visto por cualquier persona que tenga acceso al link de tu repositorio. 

Un repositorio privado es uno en el cual solo tú y las personas que añadas como colaboradores pueden tener acceso al código.

> *Volver a sección [Usar este Template](#usar-este-template)*
