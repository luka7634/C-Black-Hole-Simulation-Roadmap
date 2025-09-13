## Archivos fuente (.c) y archivos de cabecera (.h)

Cada programa en C se organiza en uno o varios ficheros fuente con extensión `.c`, que contienen la implementación de funciones y lógica de tu aplicación. Para exponer prototipos de funciones, macros, tipos de datos o constantes compartidas, utilizas ficheros de cabecera con extensión `.h`. Esta separación permite:

- Compilación incremental: solo recompilas el código modificado.
- Modularidad: aislas interfaces (headers) de implementaciones.
- Reutilización: varios `.c` pueden incluir el mismo `.h` sin duplicar código.

Al compilar, el preprocesador expande las cabeceras incluidas en cada fuente antes de generar el código objeto final.

## Función principal `main()`

La ejecución de cualquier programa en C comienza en la función `main`. Su forma más común es:

```c
int main(void) {
    /* acciones */
    return 0;
}
```

o bien con parámetros para argumentos de línea de comandos:

```c
int main(int argc, char *argv[]) {
    /* argc = número de argumentos
       argv = lista de cadenas con cada argumento */
    return 0;
}
```

Puntos clave:

- Debe devolver un `int`; un `return 0;` indica éxito.
- El sistema operativo utiliza el valor de retorno como código de salida.
- Solo puede haber una función `main` por programa; todas las demás se llaman desde ella, directa o indirectamente.

## Uso de comentarios (`//`, `/* ... */`)

Los comentarios sirven para documentar y aclarar el código sin afectar la compilación. En C tienes dos estilos:

- Comentario de línea única:
    
    ```c
    // Esto es un comentario
    ```
    
- Comentario de bloque (puede abarcar varias líneas):
    
    ```c
    /* 
       Explicación más extensa
       sobre el bloque de código.
    */
    ```
    

Los comentarios de bloque pueden anidarse conceptualmente, pero no en el código fuente: un `/*` abre y el primer `*/` cierra el comentario. Úsalos para describir módulos, explicar algoritmos o desactivar temporalmente fragmentos de código.

## Directivas de preprocesador (`#include`, `#define`)

Antes de la compilación, el preprocesador maneja líneas especiales que empiezan con `#`. Entre las más usadas están:

- `#include`: inserta el contenido de un fichero.
    
    - Ángulos `<…>` para headers del sistema:
        
        ```c
        #include <stdio.h>
        ```
        
    - Comillas `"…"` para headers locales:
        
        ```c
        #include "mi_util.h"
        ```
        
- `#define`: crea macros de texto o constantes simbólicas:
    
    ```c
    #define MAX_BUFFER 1024
    #define SQUARE(x) ((x) * (x))
    ```
    

Estas directivas permiten personalizar el código, gestionar configuraciones y habilitar compilaciones portables sin modificar múltiples ficheros fuente.