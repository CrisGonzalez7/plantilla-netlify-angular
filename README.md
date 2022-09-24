# Plantilla de Angular para Netlify
![netlify + angular logo](https://res.cloudinary.com/dzkoxrsdj/image/upload/v1646339469/angular_wzrs5o.png)

Este es un proyecto angular básico que contiene todo lo necesario para implementarlo directamente en [Netlify](https://netlify.com). 

## Table of Contents:

- [Clonar Repositorio](#clonar)
- [Netlify CLI](#netlify-cli)
  - [Compartir Proyecto](#compartir-proyecto)
  - [Token en GitHub](#token-en-github)
  - [Terminal VSCode](#terminal-vscode)
- [Subiendo a GitHub](#subiendo-a-github)
  - [Notes on Styling](#notes-on-styling)
  - [Remove Styling](#remove-styling)
- [Testing](#testing)
  - [Included Default Testing](#included-default-testing)
  - [Removing Renovate](#removing-renovate)
  - [Removing Cypress](#removing-cypress)
- [Angular + Netlify Resources](#angular--netlify-resources)

## Clonar Repositorio

Para clonar facilmente este repositorio sigue los siguientes pasos:
- Crea una carpeta en tu computador donde almacenarás el proyecto
- Abre la carpeta con [Visual Studio Code](https://code.visualstudio.com)
- Ve al menú superior de Visual Studio Code y abre un terminal
- Ejecuta el siguiente comando 

```bash
git clone https://github.com/veronica-gonzalez/plantilla-netlify-angular.git
```

- Entra a la carpeta del proyecto con el comando:

```bash
cd angular-quickstart
```

Para instalar los paquetes necesarios ejecuta el siguiente comando:

```bash
npm install
```

Para verificar que esté funcionando de manera correcta puedes levantar un servidor local con el comando:

```bash
ng serve
```

¡Ya puedes empezar a trabajar en tu proyecto!

## Netlify CLI

También puedes ejecutar tu proyecto localmente utilizando [Netlify CLI](https://docs.netlify.com/cli/get-started/)

Para iniciar la instalación sigue los siguientes pasos:
- En la terminal ejecuta:

```bash
npm install netlify-cli -g
```

> Si eres usuario de Ubuntu o alguna distribución basada en Ubuntu utiliza este comando: `sudo npm install netlify-cli -g`

- Una vez terminada la instalación puedes comprobar la versión instalada y encontrar la información básica de la herramienta con el siguiente comando: 

```bash
netlify
```

Para ejecutar tu proyecto de manera local utiliza:

```bash
netlify dev
```

### Compartir Proyecto

Para conectarte con Netlify y poder compartir tu proyecto en la web ejecuta: 

```bash
netlify init
```

Esto te abrirá una pestaña en el navegador donde deberás acceder a tu cuenta de Netlify o crear una cuenta si no la posees.

Una vez hayas ingresado a Netlify te llevará a una pantalla donde te pedirá autorizar a la aplicacción Netlify CLI, y te entregará detalles sobre los permisos que le concederás. Básicamente se trata de una autorización para que Netlify CLI pueda crear y administrar sitios en tus equipos de Netlify. Y puedes revocar el acceso cuando así lo desees. Haces clic en `Authorize`, te saldrá una pantalla en la cual se confirma que la autorización fue concedida con éxito y puedes cerrar esa pestaña del navegador. 

Volviendo a Visual Studio Code te saldrá el siguiente mensaje: 

> You are now logged into your Netlify account!

Y también te preguntará:

> How do you want to link this folder to a site?

Te saldrán dos opciones 

> ⇄  Connect this directory to an existing Netlify site 
  +  Create & configure a new site 
 
Selecciona `+  Create & configure a new site` utilizando las flechas `subir` y `bajar` de tu teclado y presiona `Enter`

Luego te aparecerá una linea que dice `Team`, selecciona el equipo que deseas utilizar y presiona `Enter`

Te aparecerá una linea que dice `Site name` y por defecto te entragará un nombre entre paréntesis, puedes cambiarlo de inmediato borrando la línea e introduciendo el nombre que deseas ponerle a tu sitio. Si no hay problemas con el nombre te saldrá un mensaje que dice `Site Created` y te entregará los siguientes detalles: 

`Admin URL`
`URL`
`Site ID`

Luego te pedirá acceso a tu cuenta de GitHub para configurar Webhooks y Deploy Keys. Puedes autorizar a través de Netlify o con un token de GitHub. Selecciona la opción que mejor te parezca. En mi caso prefiero autorizar con un Token de GitHub. 


### Token en GitHub

Para poder obtener un Token en GitHub en el menú deber ir a `settings`, luego en las opciones de la columna izquierda haces clic en `Developer Settings` luego vas a `Personal access tokens`y en la esquina superior derecha haces clic en el botón `Generate new token`. 

En Note colocas un nombre que identifique al Token, ejemplo `Token para Netlify`
En `Expiration` te recomiendo dejarlo en `30 days`
En `Select scopes`te recomiendo seleccionar todas las opciones para no tener problemas más adelante

Luego haces clic en el botón `Generate token` 

Es importante que lo copies y lo utilices de inmediato ya que GitHub no te permite tener acceso nuevamente al token. 

## Terminal VSCode

Volviendo al terminal de Visual Studio Code (VSCode) debes pegar el token de Github y luego te aparecerá una linea que dice `Your build command` y te recomiendo dejarlo por defecto, solo presiona `Enter` 

Luego te aparece otra linea que dice `Directory to deploy`, esta debes dejarla por defecto para no tener problemas al desplegar el sitio. 








`netlify dev` command for more options like receiving a live preview to share (`netlify dev --live`) and the ability to test [Netlify Functions](https://www.netlify.com/products/functions) and [redirects](https://docs.netlify.com/routing/redirects/). 

> 🚨 If you decide to change the project name be sure to change it everywhere in the project including the [Netlify configuration file, `netlify.toml`](./netlify.toml), as there are many places in Angular projects where the project name is used. A quick fix is to find/replace all instances of `angular-quickstart` with your project name.

## Deploying

There are a few ways to deploy this template:
- Click the 'Deploy to Netlify' button above 
- Use the `netlify deploy` command
- Head to the [Netlify UI](https://app.netlify.com/) to deploy via GitHub or [drag and drop](https://app.netlify.com/drop) the project folder
- Use the Netlify CLI's create from template command `netlify sites:create-template angular-quickstart` which will create a repo, Netlify project, and deploy it

## Styling

We've added some modern styling to this template using css within an external stylesheet, this will allow you to easily remove our styling and add in your own. 

If you decide that you want to keep our styling you can review our style notes below. 

### Notes on Styling

The variables below give you the ability to change the gradient colors of the blobs and are interpolated into the URL string of the background-img within the body. 

```css
// Controls the blob blur gradient colors within the main tag's svg
--top-right-blur-1: #20C6B7;
--top-right-blur-2: #4D9ABF;
--bttm-left-blur-1: #de3641;
--bttm-left-blur-2: #e46b73;
```

## Remove Styling

If you decide that our styling is not for you, all you'll need to do is remove the [demo-styling.css](https://github.com/netlify-templates/angular-quickstart/blob/tn/designUpdates/src/demo-styling.css) file. 

## Testing

### Included Default Testing

We’ve included some tooling that helps us maintain these templates. This template currently uses:

- [Renovate](https://www.mend.io/free-developer-tools/renovate/) - to regularly update our dependencies
- [Cypress](https://www.cypress.io/) - to run tests against how the template runs in the browser
- [Cypress Netlify Build Plugin](https://github.com/cypress-io/netlify-plugin-cypress) - to run our tests during our build process

If your team is not interested in this tooling, you can remove them with ease!

### Removing Renovate

In order to keep our project up-to-date with dependencies we use a tool called [Renovate](https://github.com/marketplace/renovate). If you’re not interested in this tooling, delete the `renovate.json` file and commit that onto your main branch.

### Removing Cypress

For our testing, we use [Cypress](https://www.cypress.io/) for end-to-end testing. This makes sure that we can validate that our templates are rendering and displaying as we’d expect. By default, we have Cypress not generate deploy links if our tests don’t pass. If you’d like to keep Cypress and still generate the deploy links, go into your `netlify.toml` and delete the plugin configuration lines:

```diff
[[plugins]]
  package = "netlify-plugin-cypress"
-  [plugins.inputs.postBuild]
-    enable = true
-
-  [plugins.inputs]
-    enable = false 
```

If you’d like to remove the `netlify-plugin-cypress` build plugin entirely, you’d need to delete the entire block above instead. And then make sure sure to remove the package from the dependencies using:

```bash
npm uninstall -D netlify-plugin-cypress
```

And lastly if you’d like to remove Cypress entirely, delete the entire `cypress` folder and the `cypress.config.ts` file. Then remove the dependency using:

```bash
npm uninstall cypress
```

## Angular + Netlify Resources

Here are some resources to help you on your Angular + Netlify coding fun!

- [A video walkthrough of the Angular Quick Start Template](https://youtu.be/rNAiN94bBUs)
- [A blog post on the Angular Quick Start Template](https://www.netlify.com/blog/get-started-with-angular-on-netlify-quickly)

- [Angular on Netlify Configuration Docs](https://docs.netlify.com/configure-builds/common-configurations/angular/)
- [Angular posts via the Netlify Blog](https://www.netlify.com/tags/angular/)
- [Angular in the Jamstack Tutorials](https://explorers.netlify.com/learn/angular-in-the-jamstack)

Hope this template helps :) Happy coding 👩🏻‍💻!

---

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.2.5.
