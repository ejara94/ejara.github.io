## JavaScript 

Aquí hay truquitos y conocimiento relevante que junté haciendo el curso "JavaScript Algorithms and Data Structures" en [freecodecamp.org](https://www.freecodecamp.org/learn)

### Diferencia entre let y var

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
