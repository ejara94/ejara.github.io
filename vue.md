# Vue

Conceptos principales y cosas que tuve que aprender para la memoria en Vue

## Conceptos

## Key Directives

### v-on, v-model y v-bind

Son las tres directivas potentes de Vue. Son la forma rápida de enlazar las variables de nuestro script (declaradas en `data()` ) con el DOM (Document Object Model, los tags del html, sus opciones y sus valores). Al ser declaradas en `data()`, las variables quedan disponibles para ser llamadas dentro de doble llaves `{{ }}` (interpolación) en el campo de texto entre los tags y así ser renderizadas.

El `v-bind` es una directiva que se anteapone a alguna opción de un tag para hacer que ese valor esté enlazado directamente a una variable, también declarada en el retorno de `data()`. Por ejemplo, el link de una página:

```
    <a href="www.google.com">Google</a>
```
Para este caso, con la variable `link = www.google.com`, como lo que hay que cambiar es el valor de la opción `href`, no sirve hacer:

```
    <a href="{{link}}">Google</a>
```

pasaría a ser, con v-bind:
```
    <a v-bind:href="link">Google</a>
```

`v-on` es la directiva para declarar los eventos personalizados de Vue. Al declarar por ejemplo:
```
    <button v-on:click="doSmth()">Aceptar</button>
```
Haremos que se ejecute la función `submit()` declarada en `methods` en la llave de elementos por el lado de Vue. 
Los eventos de Vue tienen modificadores predefinidos a los cuales accedemos, por ejemplo:
```
    <form v-on:submit.prevent="submitForm($event)">
        <input type="text">
        <button>Sign Up</button>
    </form>
```
En el caso anterior, el modificador `.prevent` previene el comportamiento por omisión de los formularios de recargar la página en el submit. Otro ejemplo es el `v-on:click.right` para hacer que un elemento reaccione al click derecho en vez del click izquierdo.

El `v-model` enlaza a un tag html con alguno de los elementos declarados en el retorno de `data()`. `v-model` enlaza el valor de la entrada del tag a la variable a quien apunta, asi que en resumen es lo mismo que escribir `v-bind:value v-on:input`. Es el two-way binging, de una jeje.