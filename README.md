# Guia-sass

## Inpiracion del proyecto & objetivo

- Aprende a usar Sass para crear una aplicación web.
- Entender las diferentes funciones de Sass.

<details open>
<summary >⚙️ Instalacion de sass⚙️</summary>

1. Instalamos sass  

    via npm:
    ```bash
    npm install -g sass
    ```

2. Structura de sass (ejemplo)
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
</details >


<details open>
<summary>⚙️ Como usar sass ⚙️</summary>

1. La anidacion

    > **Note**

    Como se hacia en css

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

    como se hace en sass

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
2.  Tipos de archivos scss y sass

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

1. Las variables se definen en [sass/base/_variables.scss](src/sass/base/_variables.scss).

    Se pueden definir variables de 2 formas la primera es la mas comun:

    ```sass
    $card-color: white;
    $card-height: 40vh;
    $border-min: 1vw;
    $boxshadow-left: 0px 0px 10px rgba(0,0,0,0.5);
    $basic-transition: all 0.3s ease-in-out;
    $font-family: "Roboto", sans-serif;
    $font-weight: 400;
    ```
    La segunda es la mas utilizada seria haciendo ``arrays`` de variables:
    ```sass
    $border: (
        "pequeño" : 0.5vw,
        "normal" : 1vw,
        "grande" : 10vw
    );

    $boxshadow: (
        "pequeño" : 0px 0px 10px rgba(0,0,0,0.5),
        "normal" : 0px 0px 20px rgba(0,0,0,0.5),
        "grande" : 0px 0px 30px rgba(0,0,0,0.5)
    );

    $font-weight: (
        "pequeño" : 200,
        "normal" : 400,
        "grande" : 800
    );

    ```
2. Como importar las variables a un archivo de estilos

    > **Warning**

    En cada archivo que usemos una variable debemos poner en el inicio del archivo el siguiente codigo:
    ```sass
    @use "sass/base/variables";
    ```
    Por default las variables se combierten en ``namespaces`` de forma que esto no funcionaria.

    ```sass
    @use "sass/base/variables";

    body{
        color: $card-color;
    }
    ```

    Se trendria que usar de esta forma

    ```sass
    @use "sass/base/variables";

    body{
        color: variables.$card-color;
    }
    ```

    Al ser namespace se puede cambiar el nombre.

    ```sass
    @use "sass/base/variables as v"; ******

    body{
        color: v.$card-color;
    }
    ```

    Tambien se puede hacer global ``*`` de esta forma.

    ```sass
    @use "sass/base/variables as *"; ******

    body{
        color: $card-color;
    }
    ```

    > **Warning**

    Para usar las arrays de variables debemos usar el siguiente formato map-get(nombre de la varialbe , "stylos de la array"):

    ```sass
    @use "sass/base/variables as *"; ******

    body{
        color: map-get($border, "pequeño");
    }
    ```



3. Las variables se pueden usar en cualquier archivo de estilos de la siguiente forma:

    ```sass
    .grid-item{
        background-color: $card-color;      *
        border-radius: $border-min;         *
        padding: 20px 0px 1vh;
        margin: 10px;
        box-shadow: $boxshadow-left;        *
        transition: $basic-transition;      *
        display: grid;
        justify-items: center;
        align-items: center;
        height: $card-height;               *
    &:hover{
        transform: scale(1.05);
    }
}
    ```


</details>

<details open>
<summary>⚙️  mixins ⚙️</summary>

1. Los mixins nos permiten evitar repetir codigo.

    Esto que tiene demasiado codigo repetido se puede hacer con mixins haorrando muchas lineas de codigo. 
    ```sass
    body{
        display:grid;
        height: 100vh;
        background-color: red;
        border-radius: none;

        main{
            display:grid;
            height: 100vh;
            background-color: white;
            border-radius: none;

            section{
                display:grid;
                height: 100vh;
                background-color: purple;
                border-radius: none;

                div{
                    display:grid;
                    height: 20vh;
                    background-color: white;
                    border-radius: 1vw;
                }
            }
        }
    }
    ```

2. Los mixins se definen de la siguiente forma:

    ```sass
    @mixin nombre del mixin($display, $height, $color, $radius){
        display: $display;
        box-shadow: $boxshadow;
        height: $height;
        background-color: $color;
        border-radius: $radius;
    }
    ```

    Lo mismo pero añadiendo mixins:

    ```sass
        @mixin card-shadow($display, $height, $color, $radius){
            display: $display ;
            height: $height;
            background-color: $color;
            border-radius: $radius;
        }

        body{
            @include mixin1(grid,100vh,blue,);

            main{
                @include mixin1(grid,100vh,blue,);

                section{
                    @include mixin1(flex,50vh,purple,);

                    div{
                        @include mixin1(grid,10vh,white,);
                    }
                }
            }
        }
    ```


</details>

<details open>
<summary>⚙️  loops ⚙️</summary>

## if
```sass
@if $circle {
    border-radius: $size / 2;
}
```

## if else
```sass
@if $light-theme {
    background-color: $light-background;
    color: $light-text;
} @else {
    background-color: $dark-background;
    color: $dark-text;
}
```

## while
```sass
@while $value > $base {
    $value: math.div($value, $ratio);
}
```

## for 
```sass
$count: 0;
@for $i from 0 to 3{
    #{"#"+separator#{$i}}{
        grid-area: 1/#{$i+1};

        @for $j from 0 to 9{
            #{"#"+content#{$count}}{
                display: grid;
            }
            $count: $count +1;
        }
    };
}
```
</details>
