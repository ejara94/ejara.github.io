# Flutter Tips

Apuntes basa


## Dart

Flutter es un framework de Dart, lenguaje para programación web de Google, de tipado fuerte, muy influenciado por Javascript y C++ (o C# según leí, sólo que yo nunca he visto ni un hola mundo en C# jaja). Puedes probarlo en el [DartPad](https://dartpad.dartlang.org/)

### Hola mundo

```
void main() {

    String juan = "Perez"; // puede ser var, quedaria de tipo dynamic
    print('Hola, Señor $(juan)!');

}
```

### Datos de las estructuras

Como en C++, se puede especificar los tipos que componen las estructuras, como:

```
List<int> numeros = [1, 2, 3, 4, 5];

List otraLista = List(10); //Lista de tamaño fijo, no se puede hacer .add() 
```
Los JSON se llaman Map:

```
Map persona<string, dynamic> = {
    'nombre' : 'Carlos',
    'edad'   : '32',
    'soltero': true
}

print( persona.nombre ); //No funciona
print( persona['nombre'] );
persona.addAll( { 'domicilio':'P Sherman, Calle Wallaby 42, Sidney' } );
```

Getters, Setters:

```
class Cuadrado{

    double _lado; //atributos PRIVADOS

    set lado( double valor ) {

        _lado = valor;

    }

    double get area {
        return _lado * _lado;
    }

    //double get area => _lado * _lado;

}

```
### Futures
```
void main() {
    print('Estamos a punto de pedir datos');
    httpGet('https://una_api/un_endpoint').then ( (data) {
        print(data)
    });
    print('Ultima línea');
}

Future<String> httpGet(String url) {
    return Future.delayed( new Duration( seconds: 4), () {
        return 'Hola Mundo';
    });
}

```
Ese codigo resuelve la promesa despues de los 4 segundos, sin detenerse, es decir, funciona de forma síncrona. Para que funcione de forma asíncrona hay que declarar la función con un async, y usar los await en los Future:

```
void main() async {
    print('Estamos a punto de pedir datos');
    String data = await httpGet('https://una_api/un_endpoint');

    print(data);
    print('Ultima línea');
}

Future<String> httpGet(String url) {
    return Future.delayed( new Duration( seconds: 4), () {
        return 'Hola Mundo';
    });
}


```