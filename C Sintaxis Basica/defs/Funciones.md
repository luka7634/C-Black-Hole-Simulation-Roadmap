## Declaración y definición de funciones

Antes de usar una función debes declararla (prototipo) y luego definirla (implementación), o bien definirla antes de su primera llamada. Esto ayuda al compilador a verificar tipos y evitar errores de “función no declarada”.

Sintaxis del prototipo:

```c
tipo_retorno nombre_función(tipo1, tipo2, …);
```

Sintaxis de la definición:

```c
tipo_retorno nombre_función(tipo1 param1, tipo2 param2, …) {
    // cuerpo de la función
}
```

---

## Parámetros y valores de retorno

Las funciones pueden recibir cero o más parámetros y devolver un valor.

- Parámetros:
    
    - Se especifican en la lista de la definición.
    - Pueden usarse como variables locales dentro de la función.
- Valor de retorno:
    
    - Declarado antes del nombre de la función.
    - Se envía al llamador con `return <expr>;`.
    - Una función `void` no devuelve valor.

Ejemplo:

```c
int sumar(int a, int b) {
    return a + b;
}

void saludar(void) {
    printf("¡Hola!\n");
}
```

---

## Ámbito de variables: local y global

El ámbito determina dónde es visible una variable:

- Local:
    
    - Declarada dentro de una función o bloque `{ … }`.
    - Solo existe mientras ese bloque se ejecuta.
- Global:
    
    - Declarada fuera de todas las funciones.
    - Visible desde cualquier función tras su declaración.

Ejemplo:

```c
int contador_global = 0;  // variable global

void foo(void) {
    int contador_local = 5;  // variable local
    contador_global++;
}
```

---

## Prototipos de funciones

Un prototipo informa al compilador del nombre, tipo de retorno y parámetros de una función antes de su definición. Sin ellos, C asume un retorno `int` y no valida los argumentos, lo que puede provocar comportamientos indeseados.

- Se suelen colocar en archivos `.h`:
    
    ```c
    // utilidades.h
    int procesar(int dato);
    ```
    
- Luego inclúyelos en el `.c`:
    
    ```c
    #include "utilidades.h"
    ```
    
- Facilitan la compilación incremental y la comprobación de tipos temprana.
    

---

# Ejemplo de Librería Modular en C

A continuación encontrarás una librería sencilla llamada **mathlib** que ofrece funciones matemáticas básicas. La estructura de directorios queda así:

```
mathlib/
├── include/
│   └── mathlib.h
├── src/
│   └── mathlib.c
├── examples/
│   └── main.c
└── Makefile
```

---

## 1. Archivo de cabecera (include/mathlib.h)

```c
#ifndef MATHLIB_H
#define MATHLIB_H

/* Devuelve la suma de dos enteros */
int ml_sum(int a, int b);

/* Devuelve el factorial de n (n >= 0) */
long ml_factorial(int n);

#endif /* MATHLIB_H */
```

- Uso de **include guard** para evitar inclusiones múltiples.
- Prototipos de las funciones públicas de la librería.

---

## 2. Implementación (src/mathlib.c)

```c
#include "mathlib.h"

int ml_sum(int a, int b) {
    return a + b;
}

long ml_factorial(int n) {
    if (n < 0) return -1;  /* valor de error */
    long result = 1;
    for (int i = 2; i <= n; i++) {
        result *= i;
    }
    return result;
}
```

- Incluimos el header local con comillas `"mathlib.h"`.
- Definimos las funciones declaradas.

---

## 3. Programa de ejemplo (examples/main.c)

```c
#include <stdio.h>
#include "../include/mathlib.h"

int main(void) {
    int x = 5, y = 7;
    printf("ml_sum(%d, %d) = %d\n", x, y, ml_sum(x, y));

    int n = 6;
    long f = ml_factorial(n);
    if (f < 0) {
        printf("Error: factorial de un número negativo\n");
    } else {
        printf("ml_factorial(%d) = %ld\n", n, f);
    }

    return 0;
}
```

- Incluye el header de la librería para usar sus funciones.
- Muestra manejo básico de retorno de error en `ml_factorial`.

---

## 4. Makefile

```makefile
CC      := gcc
CFLAGS  := -Iinclude -Wall -Wextra -O2
SRC     := src/mathlib.c
OBJ     := $(SRC:.c=.o)
TARGET  := libmathlib.a

# Genera la librería estática
$(TARGET): $(OBJ)
    ar rcs $@ $^

# Compila el objeto de la librería
src/%.o: src/%.c
    $(CC) $(CFLAGS) -c $< -o $@

# Compila y enlaza el ejemplo con la librería
.PHONY: example
example: $(TARGET)
    $(CC) $(CFLAGS) -L. -lmathlib examples/main.c -o examples/run_example

# Limpieza de archivos compilados
.PHONY: clean
clean:
    rm -f src/*.o $(TARGET) examples/run_example
```

- `libmathlib.a` queda disponible para enlazar.
- Target `example` genera el ejecutable en `examples/run_example`.
- `clean` borra objetos, la librería y el ejecutable.

---

Con esto tienes una librería modular y reusable.

Si quieres, podemos añadir:

- Test unitarios con un framework como **CMocka**.
- Documentación automátic­a con **Doxygen**.
- Versión dinámica (`.so`) y scripts de instalación.

Dime qué te interesa y lo armamos.