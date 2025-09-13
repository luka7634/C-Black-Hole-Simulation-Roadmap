## Memoria en un programa C

Un proceso en ejecución divide su espacio de direcciones en segmentos:

- Código (instrucciones)
- Datos estáticos (variables globales y estáticas)
- Stack (variables locales y llamadas a funciones)
- Heap (memoria dinámica)

La memoria dinámica se reserva y libera en tiempo de ejecución mediante funciones de la biblioteca estándar. Esto permite estructuras de datos de tamaño variable y vida útil controlada por el programador.

## Funciones de asignación y liberación

Todas estas rutinas están definidas en `<stdlib.h>`.

|Función|Prototipo|Descripción|
|---|---|---|
|malloc|`void *malloc(size_t size);`|Reserva un bloque de `size` bytes|
|calloc|`void *calloc(size_t n, size_t size);`|Reserva `n` bloques de `size` bytes e inicializa a cero|
|realloc|`void *realloc(void *ptr, size_t size);`|Cambia el tamaño del bloque apuntado por `ptr` a `size` bytes|
|free|`void free(void *ptr);`|Libera el bloque previamente reservado|

### malloc

```c
int *arr = malloc(10 * sizeof *arr);
if (!arr) {
    perror("malloc failed");
    exit(EXIT_FAILURE);
}
```

`malloc` devuelve un puntero a un bloque sin inicializar o `NULL` si falla.

### calloc

```c
int *zeros = calloc(10, sizeof *zeros);
```

`calloc` garantiza que todos los bytes estén puestos a cero.

### realloc

```c
int *nuevo = realloc(arr, 20 * sizeof *arr);
if (!nuevo) {
    free(arr);
    perror("realloc failed");
    exit(EXIT_FAILURE);
}
arr = nuevo;
```

`realloc` conserva contenido previo hasta el nuevo tamaño, o devuelve `NULL` y deja intacto el bloque original.

### free

```c
free(arr);
arr = NULL;
```

Libera memoria en el heap. Siempre maneja el puntero con cuidado para evitar dobles liberaciones o accesos a memoria liberada (dangling pointers).

## Punteros y memoria dinámica

Al usar estas funciones, trabaja siempre con punteros que apunten al tipo adecuado. Por ejemplo:

```c
struct Nodo {
    int dato;
    struct Nodo *siguiente;
};

struct Nodo *nodo = malloc(sizeof *nodo);
nodo->dato = 5;
nodo->siguiente = NULL;
```

Evita convertir el resultado de `malloc` en C. El casting es innecesario y puede ocultar errores de falta de inclusión de `<stdlib.h>`.

## Buenas prácticas

- Comprueba siempre el valor devuelto por `malloc`, `calloc` o `realloc`.
- Usa `free` exactamente una vez por bloque reservado y pon el puntero a `NULL` tras la liberación.
- Para estructuras complejas, sigue un patrón de limpieza que libere en orden inverso al de la asignación.
- Emplea herramientas como Valgrind o Sanitizers para detectar fugas y accesos ilegales en tiempo de ejecución.

---

Con estos fundamentos podrás crear estructuras dinámicas como vectores redimensionables, listas enlazadas y árboles, gestionando tú mismo la vida y el tamaño de cada bloque de memoria en C.