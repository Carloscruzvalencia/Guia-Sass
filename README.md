# Guia-sass

## Inpiracion del proyecto & objetivo

- Aprende a usar Sass para crear una aplicación web.
- Entender las diferentes funciones de Sass.

El diseño web se ha creado en [Figma](https://www.figma.com/file/kP0SJhf4iDDa9kAzsz1LM1/Github-projects?node-id=0%3A1) por Carlos cruz valencia

## Tecnologias usadas

- Ide
    <!-- visual studio code -->
    <code><img height="25" src="https://img.shields.io/badge/Visual_Studio_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white"></code>

- lenguajes/frameworks usados
    <!-- bootstrap -->
    <!-- html -->
    <code><img height="30" src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"></code><!-- css -->
    <code><img height="30" src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"></code><!-- sass -->
    <code><img height="30" src="https://img.shields.io/badge/Sass-CC6699?style=for-the-badge&logo=sass&logoColor=white"></code>

## Vista previa del proyecto

``vista no disponible``
<!-- <img src="project-preview.png" aling="center"></img> -->
<!-- <img src="project-preview.gif" aling="center"></img> -->

## Estado del proyecto

|Trabajando en el proyecto|✔️|
| -------------------------- | :----------------: |

<!-- <details> el desplegable estara desactivado -->
<!-- <details open> el desplegable estara activo -->

<details open>
<summary>⚙️ Instalacion y integracion de sass en react ⚙️</summary>

1. Crearmos el proyecto de react
   
   ```npx create-react-app nombre-del-proyecto```

2. Instalamos sass  

    via npm:
    ```bash
    npm i sass
    ```

3. Structura de sass (ejemplo)
    ```text
    /
    └── src/
         └── sass/
              ├── base/
              ├── components/
              ├── layouts/
              └── main.scss
    ```

    ``sass`` Es el directorio de los archivos de estilos en sass. [sass](src/sass/)

    
    - ``base`` Es el directorio de los archivos de configuracion de sass. [sass/base](src/sass/base/)

      ``components`` Es el directorio donde se guardan los archivos de los diferentes componentes. (buttons, cards, etc) [sass/components](src/sass/components/)

      ``layouts`` Es el directorio donde se guardan los archivos de los diferentes layouts. (header, footer, etc) [sass/layouts](src/sass/layouts/)

      ``main.scss`` Es el archivo de estilos principal. [sass/main.scss](src/sass/main.scss)

4. Integramos sass en nuestro proyecto
   
   En el archivo [app.js](src/app.js) en la carpeta [src](src) agregamos el siguiente codigo:
   ```js
    import './sass/main.scss';
    ```
</details >


<details open>
<summary>⚙️ Como usar sass ⚙️</summary>

1. La sintaxis de sass

    Si el archivo de estilos es ``main.scss``, entonces la sintaxis es:
    ```scss
    body{
        color: #fff;
        background-color: #000;
        main{
            color: #fff;
            background-color: #000;
            nav{
                color: #fff;
                background-color: #000;
                ul{
                    li{
                        color: #fff;
                        background-color: #000;
                    }
                }
        
            }
            header{
                color: #fff;
                background-color: #000;
            }
            footer{
                color: #fff;
                background-color: #000;
            }
        }
    }
    ```
    > **Note**
    <details open>
    <summary>⚙️ Como seria en CSS ⚙️</summary>
    
    ```css
            body {
            color: #fff;
            background-color: #000;
            }
            body main {
                color: #fff;
                background-color: #000;
            }
            body main nav {
                color: #fff;
                background-color: #000;
            }
            body main nav ul li {
                color: #fff;
                background-color: #000;
            }
            body main header {
                color: #fff;
                background-color: #000;
            }
            body main footer {
                color: #fff;
                background-color: #000;
            }
    ```
    </details >

    Si el archivo de estilos es ``main.sass``, entonces la sintaxis es:

    ```sass
    body
      color: #fff
      background-color: #000
  
      main
          color: #fff
          background-color: #000
  
          nav
          color: #fff
          background-color: #000
  
          ul
              li
              color: #fff
              background-color: #000
  
          header
          color: #fff
          background-color: #000
  
          footer
          color: #fff
          background-color: #000
    ```
    > **Warning**
    En los archivos ``.sass`` no se usan los caracteres ``{`` ``}`` ``;``.

3. Diferencia entre archivos con ``_``landing.scss y archivos sin landing.scss

    En sass si un archivo enpieza con ``_``landing.scss no se genera un archivo con el mismo nombre.

    ```text
        /scss
            ├──style.scss
            └──_landing.scss
        /css
            ├──style.css
            └──style.css.map
    ```

    > **Warning**

    Pero si un archivo no tiene el caracter ``_`` landing.scss se genera un archivo con el mismo nombre.

    ```text
        /scss
            ├──style.scss
            └──landing.scss
        /css
            ├──style.css
            ├──style.css.map
            ├──landing.scss       Archivos generados al compilar sass  
            └──landing.scss.map   Archivos generados al compilar sass
    ```

    > **Note**

    Esto puede ser util en algunos casos.

4. @use o @import
    
    > **Note**
    En sass no usamos @import se puede usar pero ``no es recomendado``.

    > **Warning**

    Con ❗❗@import❗❗
    ```sass
    @import "sass/layouts/landing.scss";
    ```
    > **Note**
    
    con ✔️✔️ @use ✔️✔️
    ```sass
    @use "sass/layouts/landing.scss";
    ```

5. todos los @use se suelen hacer en el archivo principal de estilos.

    > **Note**
    El archivo main.scss normalmente deveria verse asi:

    ```sass
    @use "base/settings.scss";
    @use "components/button.scss";
    @use "layouts/landing.scss";
    ```
    [main.scss](src/sass/main.scss)
</details >

<details open>
<summary>⚙️ variables ⚙️</summary>

1. Las variables se definen en el archivo de configuracion de sass.

    ```sass
    $primary-color: #fff;
    $secondary-color: #000;
    $tertiary-color: #fff;
    $quaternary-color: #000;
    ```

</details>

<!-- └── / ├── │ -->


## Licencia

Este proyecto está bajo la Licencia (MIT) - mira el archivo [LICENSE.md](LICENSE.md)  para mas detalles

<!-- ## !codigo temporal¡
## git update code
```shell
git add -A && git commit -a -m \"update\" && git push
```

## sass compiler code
```shell
sass -w --style compressed assets/styles/sass/main.scss assets/styles/css/main.css
``` -->

<!-- emojis  -->
<!-- https://tutorialmarkdown.com/emojis -->
