# Vue

Conceptos principales y cosas que tuve que aprender para la memoria en Vue

## Conceptos

## Key Directives

### v-model y v-bind

Son la forma rápida de enlazar las variables de nuestro script con el DOM (Document Object Model, los tags del html, sus opciones y sus valores). El `v-model` enlaza a un tag html con alguno de los elementos declarados en el retorno de `data()`. Luego, ese elemento queda disponible para ser llamado dentro de doble llaves `{{ }}` (interpolación) y así ser renderizado. El `v-bind` es una directiva que se anteapone a alguna opción de un tag para hacer que ese valor esté enlazado directamente a una variable, también declarada en el retorno de `data()`. Por ejemplo, el link de una página:

```
<a href="www.google.com">Google</a>
```

pasaría a ser, con la variable `link = www.google.com`:
```
<a v-bind:href="link">Google</a>
```
