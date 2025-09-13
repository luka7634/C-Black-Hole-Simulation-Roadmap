## Tipos primitivos

Los tipos primitivos definen el formato y el rango de los datos que tu programa puede almacenar. Los principales en C son:

- `int`
- `float`
- `double`
- `char`

Estos tipos sirven para:

- `int`: números enteros sin decimales.
- `float`: números con decimales de precisión simple (sufijo `f`).
- `double`: números con decimales de doble precisión.
- `char`: un solo carácter (almacena su código ASCII).

Ejemplo de declaración e impresión de cada tipo:

```c
#include <stdio.h>

int main(void) {
    int    entero   = 42;
    float  flotante = 3.14f;
    double doble    = 3.1415926535;
    char   caracter = 'A';

    printf("entero: %d\n", entero);
    printf("flotante: %.2f\n", flotante);
    printf("doble: %.10f\n", doble);
    printf("caracter: %c\n", caracter);

    return 0;
}
```

---

## Declaración y asignación de variables

En C, antes de usar una variable debes:

1. Declarar su tipo y nombre.
2. (Opcional) Asignarle un valor inicial.

Sintaxis:

```c
tipo nombre;            // declaración
tipo nombre = valor;    // declaración e inicialización
```

Ejemplos:

```c
int    contador;         // solo declarada
float  promedio = 0.0f;  // declarada e inicializada
char   letra   = 'Z';    // declarada e inicializada
```

La declaración reserva espacio en memoria según el tipo, y la inicialización asigna el primer valor antes de su uso en el programa.

---

## Constantes (const, #define)

Para valores que no cambian, usa:

- `const`
    
    ```c
    const int MAX_USUARIOS = 100;
    ```
    
- `#define`
    
    ```c
    #define BUFFER_SIZE 1024
    #define SQR(x)       ((x) * (x))
    ```
    

Diferencias clave:

- `const` crea una variable de solo lectura con tipo comprobado por el compilador.
- `#define` es una simple sustitución de texto durante el preprocesado, sin tipo ni ámbito.

---

## Conversión de tipos (casting)

El casting convierte el tipo de una expresión a otro tipo explícitamente. Sintaxis:

```c
(tipo_destino) expresión
```

Ejemplos:

```c
int    a = 5;
int    b = 2;
float  resultado1 = a / b;             // división entera: resultado1 == 2.0
float  resultado2 = (float)a / b;      // casteo antes de dividir: resultado2 == 2.5

double x = 3.14;
int    y = (int)x;                     // truncate decimal: y == 3
```

Usa el casting cuando necesites precisión distinta o evitar conversiones implícitas que descarten parte del valor.