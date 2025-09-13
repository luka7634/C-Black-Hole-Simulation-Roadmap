## Imprimir en pantalla: `printf`

La función `printf` (definida en `<stdio.h>`) envía texto formateado a la salida estándar y devuelve el número de caracteres escritos.  
Su prototipo es:

```c
int printf(const char *format, ...);
```

Donde `format` es una cadena con texto literal y especificadores que se reemplazan por los valores de los argumentos siguientes.

### Especificadores comunes

|Especificador|Descripción|
|---|---|
|%d, %i|Entero con signo (int)|
|%u|Entero sin signo (unsigned int)|
|%f|Punto flotante (float)|
|%lf|Punto flotante doble (double)|
|%c|Carácter (char)|
|%s|Cadena de caracteres (char *)|
|%x|Hexadecimal sin signo (unsigned)|
|%o|Octal sin signo (unsigned)|
|%p|Puntero / dirección de memoria|

### Ejemplo básico

```c
#include <stdio.h>

int main(void) {
    int    edad    = 30;
    double pi      = 3.14159;
    char   inicial = 'R';

    printf("Edad: %d\n", edad);
    printf("Valor de pi: %.2f\n", pi);
    printf("Inicial: %c\n", inicial);
    return 0;
}
```

---

## Leer desde teclado: `scanf`

La función `scanf` lee datos de la entrada estándar (teclado) usando el formato indicado y almacena los valores en las direcciones de memoria de las variables pasadas como argumentos.  
Su prototipo es:

```c
int scanf(const char *format, ...);
```

- Cada especificador en `format` debe corresponder a un puntero al tipo adecuado.
- Usa `&` ante variables escalares para pasar su dirección; no ante arrays.
- Devuelve el número de elementos leídos correctamente.

### Ejemplo de uso

```c
#include <stdio.h>

int main(void) {
    int edad;
    char nombre[32];

    printf("Introduce tu edad: ");
    if (scanf("%d", &edad) != 1) {
        fprintf(stderr, "Error de lectura de edad\n");
        return 1;
    }

    printf("Introduce tu nombre: ");
    scanf("%31s", nombre);  // evita desbordar el buffer

    printf("Hola %s, tienes %d años\n", nombre, edad);
    return 0;
}
```

---

## Formateo de cadenas y números

`printf` y `scanf` permiten controlar ancho de campo, alineación, relleno y precisión mediante modificadores entre `%` y el especificador de tipo:

- **Ancho de campo**: número mínimo de caracteres que ocupará la salida.
- **Alineación**: `-` (izquierda) o predeterminado (derecha).
- **Relleno**: `0` para rellenar con ceros si el valor es más corto.
- **Precisión**: `.[n]` para definir dígitos decimales (floats) o longitud máxima (strings).

### Ejemplos de formateo

```c
printf("|%10s|\n", "Roybel");    // ancho 10, alineado a la derecha
printf("|%-10s|\n", "Roybel");   // ancho 10, alineado a la izquierda
printf("%04d\n", 42);            // relleno con ceros, imprime "0042"
printf("%.3f\n", 3.14159);       // tres decimales, imprime "3.142"
printf("%8.2f\n", 3.14);         // ancho 8, dos decimales, imprime "    3.14"
```

Para `scanf`, puedes usar anchos máximos para cadenas:

```c
char buf[16];
scanf("%15s", buf);  // lee hasta 15 caracteres + '\0'
```

---

Con estos fundamentos de entrada y salida podrás interactuar con el usuario y controlar con precisión cómo se presentan y reciben los datos en tus programas en C.

¿Te gustaría ver un ejercicio práctico que combine lectura y formateo avanzado, o prefieres profundizar en manejo de errores y buffers?