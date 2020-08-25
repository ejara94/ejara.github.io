# JavaScript 

Aquí hay truquitos y conocimiento relevante que junté haciendo el curso "JavaScript Algorithms and Data Structures" en [freecodecamp.org](https://www.freecodecamp.org/learn)

## Diferencia entre let y var

### Sobreescritura 

Con `var`, las declaraciones se pueden sobreescribir, y no tira error. Entonces, se agrega en ES6 el `let` para poder hacer declaraciones no sobreescribibles.
```
var saludo = 'holi';
var saludo = 'teni pololi';
```
... nada mal.
```
let saludo = 'holi';
let saludo = 'teni pololi';
```
... explota!

### La volaita del scope

```
var printNumTwo;
for (var i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
// returns 3
```
Como dice el código sacado _textual_ del curso, la llamada a la función printNumTwo() retorna 3. Declarar variables con `var` les da acceso global, o en la función donde se declaran; en su _scope_. Esto es ambiguo para algunas expresiones, como el valor inicial de la variable de iteración del `for`. En estos casos en que se declaran variables en las condiciones del `for`, la variable `i` se modifica globalmente, en este caso, hasta 3 y ese es su valor terminado el ciclo `for`, asi mismo, cuando se accede a ella en la llamada a `printNumTwo`. Y esto independiente de que la definición de la función `printNumTwo` haya sido en `i===2` ! 

Perooo, con el buen ´let´:
```
'use strict';
let printNumTwo;
for (let i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
// returns 2
console.log(i);
// returns "i is not defined"
```

**\#dato:** `'use strict;'` activa el [Modo Estricto](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Modo_estricto) 
Bueno... por qué declararías una función dentro de un for? Podríamos querer distintas declaraciones de una misma función según algún valor, una promesa, who knows.
