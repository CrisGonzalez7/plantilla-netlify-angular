# Plantilla de Angular para Netlify
![netlify + angular logo](https://res.cloudinary.com/dzkoxrsdj/image/upload/v1646339469/angular_wzrs5o.png)

Este es un proyecto angular básico que contiene todo lo necesario para implementarlo directamente en [Netlify](https://netlify.com). 

## Índice:

- [Clonar Repositorio](#clonar-repositorio)
- [Netlify CLI](#netlify-cli)
  - [Compartir Proyecto](#compartir-proyecto)
  - [Token en GitHub](#token-en-github)
  - [Terminal VSCode](#terminal-vscode)
- [Subiendo a GitHub](#subiendo-a-github)
- [Configurando Repositorio Personal](#configurando-repositorio-personal)
  - [Primer Commit](#primer-commit)
  - [Mezclando con Main](#mezclando-con-main)
- [Configurando Netlify con GitHub](#configurando-netlify-con-github)

## Clonar Repositorio

Para clonar facilmente este repositorio sigue los siguientes pasos:
- Crea una carpeta en tu computador donde almacenarás el proyecto
- Abre la carpeta con [Visual Studio Code](https://code.visualstudio.com)
- Ve al menú superior de Visual Studio Code y abre un terminal
- Ejecuta el siguiente comando 

```bash
git clone https://github.com/veronica-gonzalez/plantilla-netlify-angular.git
```

- Para cambiarle el nombre a tu proyecto ejecuta:

```bash
mv plantilla-netlify-angular [NOMBRE DE TU PROYECTO] 
```

- Luego, entra a la carpeta del proyecto con el comando:

```bash
cd [NOMBRE CARPETA]
```

Para instalar los paquetes necesarios ejecuta el siguiente comando:

```bash
npm install
```

Para verificar que esté todo funcionando de manera correcta, puedes levantar un servidor local con el comando:

```bash
ng serve
```

> Si te lanza el siguiente mensaje `? Port 4200 is already in use. Would you like to use a different port?` pon la letra `y` y presiona `enter`

Si todo salió correctamente, te debería lanzar el siguiente mensaje `** Angular Live Development Server is listening on localhost:[NUMERO], open your browser on http://localhost:[NUMERO]/ **`

Puedes ingresar directamente al link haciendo clic con la tecla `ctrl` presionada. 

¡Ya puedes empezar a trabajar en tu proyecto!

## Netlify CLI

También puedes ejecutar tu proyecto localmente utilizando [Netlify CLI](https://docs.netlify.com/cli/get-started/)

Para iniciar la instalación sigue los siguientes pasos:

- Abre un nuevo terminal haciendo clic en `+`en la sección de la terminal de Visual Studio Code. 

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

Una vez hayas ingresado a Netlify, te llevará a una pantalla donde te pedirá autorizar a la aplicacción Netlify CLI, y te entregará detalles sobre los permisos que le concederás. Básicamente se trata de una autorización para que Netlify CLI pueda crear y administrar sitios en tus equipos de Netlify. Y puedes revocar el acceso cuando así lo desees. 
Haces clic en `Authorize`, y te saldrá una pantalla en la cual se confirma que la autorización fue concedida con éxito; ya puedes cerrar esa pestaña del navegador. 

Volviendo a Visual Studio Code te saldrá el siguiente mensaje: 

> You are now logged into your Netlify account!

Y también te preguntará:

> How do you want to link this folder to a site?

Te saldrán dos opciones 

> ⇄  Connect this directory to an existing Netlify site 
>  +  Create & configure a new site 
 
Selecciona `+  Create & configure a new site` utilizando las flechas `subir` y `bajar` de tu teclado y presiona `Enter`

Luego te aparecerá una linea que dice `Team`, selecciona el equipo que deseas utilizar y presiona `Enter`

Te aparecerá una linea que dice `Site name`, y por defecto te entragará un nombre entre paréntesis, puedes cambiarlo de inmediato borrando la línea e introduciendo el nombre que deseas ponerle a tu sitio. Si no hay problemas con el nombre elegido, te saldrá un mensaje que dice `Site Created` y te entregará los siguientes detalles: 

`Admin URL`

`URL`

`Site ID`

Puedes hacer clic en el link de `Admin URL` y acceder a las configuraciones de tu sitio. También puedes hacer clic en el link de `URL` y ver el sitio desplegado. 

Luego te pedirá acceso a tu cuenta de GitHub para configurar Webhooks y Deploy Keys. Puedes autorizar a través de Netlify o con un token de GitHub. Selecciona la opción que mejor te parezca. En mi caso prefiero autorizar con un Token de GitHub. 

### Token en GitHub

Para poder obtener un Token en GitHub, en el menú debes ir a `settings`, luego en las opciones de la columna izquierda haces clic en `Developer Settings`. Después vas a `Personal access tokens` y en la esquina superior derecha haces clic en el botón `Generate new token`. 

En `Note` colocas un nombre que identifique al Token, ejemplo `Token para Netlify`
En `Expiration` te recomiendo dejarlo en `30 days`
En `Select scopes` te recomiendo seleccionar todas las opciones para no tener problemas más adelante

Luego haces clic en el botón `Generate token` 

🚨 Es importante que lo copies y lo utilices de inmediato ya que GitHub no te permite tener acceso nuevamente al token. 

## Terminal VSCode

Volviendo al terminal de Visual Studio Code (VSCode), debes pegar el token de Github y luego te aparecerá una linea que dice `Your build command` y te recomiendo dejarlo por defecto, solo presiona `Enter` 

Luego te aparece otra linea que dice `Directory to deploy`, esta debes dejarla por defecto para no tener problemas al desplegar el sitio. 

Si todo ha salido bien te aparecerá un mensaje que dice `Success! Netlify CI/CD Configured!`

Y si ejecutas el comando 

```bash
netlify open
```

Te abre una pestaña en el navegador con la página de administración de tu sitio. 

## Configurando Repositorio Personal

En este momento el sitio está linkeado al repositorio original, para poder linkearlo a un repositorio personal debes seguir los siguientes pasos: 

- Debes ir a [GitHub](https://github.com/), ingresar con tus datos o crear una cuenta si aún no estás logueado.
- En la esquina superior derecha de tu perfil de GitHub, hacer clic en el botón `+`
- Ingresar a `New repository`
- En `Repository name` ingresa el nombre con el que deseas identificar a tu sitio
- Luego ingresa a `Create repository`

# Editar aquí

- En `Code` copia la URL que aparece en `HTTPS`

En el terminal de VSCode ejecuta el siguiente comando: 

```bash
git remote set-url origin [PEGA AQUÍ LA URL QUE COPIASTE DE GITHUB]
```

Verifica si se actualizó la URL con el siguiente comando: 


```bash
git remote -v
```

Debe aparecer la URL de tu GitHub

### Primer Commit

# Revisar esta parte

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

Para poder subir los cambios a GitHub ejecuta: 


```bash
git pull --allow-unrelated-histories origin [NOMBRE DE LA RAMA]
```

Y luego: 


```bash
git push -u origin [NOMBRE DE LA RAMA]
```

### Mezclando con Main 

Para mezclar la rama creada con la rama main (que es la principal), debes ir al link de tu repositorio en GitHub (si lo olvidaste puedes acceder a él con el comando `git remote -v`) y es probable que te aparezca un mensaje como este ` [NOMBRE DE LA RAMA] had recent pushes [TIEMPO] ago`, y al lado un botón que diga `Compare & pull request`

Si no te sale ese mensaje puedes hacer clic en `main` luego ir a la rama en cuestión y en `contribute` hacer clic en `Open Pull Request`

En Write puedes escribir una descripción de tu proyecto si quieres y presionar `Create pull request`

Luego si te dice `This branch has no conflicts with the base branch` significa que está todo correcto y al hacer clic en `Merge pull request` y luego en `Confirm merge` los cambios serán enviados a la rama `main`

Puedes ir a la pestaña `Code` para ver los cambios

## Configurando Netlify con GitHub

En este momento tu proyecto en Netlify está linkeado con el [repositorio original] (https://github.com/veronica-gonzalez/plantilla-netlify-angular), para modificar esto en la terminal de VSCode escribe el siguiente comando 

```bash
netlify open
```

Esto te abrirá una pestaña en el navegador con la página de administración de tu sitio. 

Para que compruebes desde dónde se está desplegando tu sitio, debajo del link de tu web haz clic en `GitHub`, esto te abrirá el repositorio al cual está linkeado.

Para modificarlo vuelve a Netlify y haz clic en `Site Settings`. Luego en el menú de tu izquierda haz clic en `Build & Deploy`. Luego en `Manage repository` ve a `Link to a different repository` y conecta GitHub con Netlify. Selecciona el repositorio que quieras linkear con Netlify. Si no te aparece puedes hacer clic en `Can’t see your repo here? Configure the Netlify ap on GitHub`.

Luego que hayas elegido el repositorio, en la siguiente pantalla dejas la confguraión tal como está y haces clic en `Deploy site`.

Esperas a que termine de trabajar (puedes verificar el estado del sitio en `Production deploys`, y recargar la página hasta que diga `Publisher`. Haz clic en GitHub para verificar el repositorio linkeado y por último, haz clic en el link de tu sitio para verificar que se haya desplegado de forma correcta.

Desde este momento. cada vez que actualices la rama `Main` los cambiios se verán reflejados en Netifly de forma automática. 
