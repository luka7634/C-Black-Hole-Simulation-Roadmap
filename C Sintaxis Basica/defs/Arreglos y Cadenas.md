## Declaración y uso de arreglos

Los arreglos en C son estructuras homogéneas de acceso contiguo que almacenan un conjunto finito de elementos del mismo tipo. Se indexan desde 0 hasta `tamaño – 1` y su tamaño se determina en tiempo de compilación.

### Arreglos unidimensionales

```c
int numeros[5];           // declara un arreglo de 5 enteros
float temperaturas[10];   // declara un arreglo de 10 floats
char letras[] = {'a','b','c','d'}; // tamaño inferido: 4
```

- Acceso: `numeros[0]` … `numeros[4]`
- El último índice es `tamaño – 1`.

### Arreglos multidimensionales

```c
int matriz[3][4]; // 3 filas, 4 columnas
```

- Se almacena en memoria como un bloque lineal:
    - `matriz[0][0]`, `matriz[0][1]`, …, `matriz[0][3]`, `matriz[1][0]`, …
- Útil para tablas, imágenes o datos tabulares.

---

## Manipulación de cadenas de caracteres (`char[]`)

En C, una cadena es un arreglo de caracteres terminado en el carácter nulo `'\0'`. Esto permite determinar su fin y operar con funciones estándar.

Formas de declarar e inicializar:

```c
char saludo1[] = "Hola";       // 5 caracteres + '\0' => tamaño 5
char saludo2[10] = "Mundo";    // espacio extra rellenado con '\0'
char saludo3[6] = {'H','o','l','a','\0'}; // inicialización manual
```

- Siempre reserva un espacio para `'\0'`.
- Puedes modificar caracteres: `saludo1[0] = 'h';`

---

## Funciones estándar para cadenas

Para manipular cadenas incluye `<string.h>` y usa estas funciones clave:

|Función|Descripción|Prototipo|
|---|---|---|
|strlen|Devuelve la longitud (nº caracteres antes de `'\0'`).|`size_t strlen(const char *s);`|
|strcpy|Copia la cadena `src` (incluye `'\0'`) en `dest`.|`char *strcpy(char *dest, const char *src);`|
|strcmp|Compara `s1` y `s2` lexicográficamente; 0 si son iguales, <0 si `s1<s2`, >0 si `s1>s2`.|`int strcmp(const char *s1, const char *s2);`|
|strcat|Concatena `src` al final de `dest` (asegura espacio en `dest`).|`char *strcat(char *dest, const char *src);`|
|strncpy|Copia como máximo `n` caracteres de `src` a `dest`, no garantiza `'\0'` si `n` ≤ longitud.|`char *strncpy(char *dest, const char *src, size_t n);`|

Estos métodos facilitan la gestión de longitud, copia y comparación de cadenas sin implementar bucles manualmente.

---

## Ejemplo práctico

```c
#include <stdio.h>
#include <string.h>

int main(void) {
    char a[20] = "Hola";
    char b[]    = "Mundo";
    char c[40];

    printf("a: %s (len=%zu)\n", a, strlen(a));
    strcpy(c, a);              // c == "Hola"
    strcat(c, " ");            
    strcat(c, b);              // c == "Hola Mundo"
    printf("c: %s\n", c);
    
    int cmp = strcmp(a, b);
    if (cmp == 0) {
        printf("a y b son iguales\n");
    } else if (cmp < 0) {
        printf("a viene antes que b\n");
    } else {
        printf("a viene después de b\n");
    }
    return 0;
}
```

Con esto dominas cómo declarar, acceder y manipular tanto arreglos genéricos como cadenas de texto en C.