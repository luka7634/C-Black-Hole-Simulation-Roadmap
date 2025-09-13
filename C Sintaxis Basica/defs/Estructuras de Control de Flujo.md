## 5.1 Condicionales

Las estructuras condicionales permiten ejecutar bloques de código según si ciertas expresiones son verdaderas o falsas.

### if / else if / else

```c
if (condición1) {
    // se ejecuta si condición1 es distinta de cero
}
else if (condición2) {
    // se ejecuta si condición1 es falsa y condición2 es verdadera
}
else {
    // se ejecuta si todas las condiciones anteriores son falsas
}
```

- Las condiciones se evalúan en orden.
- Solo un bloque (el primero verdadero) se ejecuta.
- Puedes encadenar tantos `else if` como necesites.

### switch

```c
switch (expresión_entera) {
    case valor1:
        // código para valor1
        break;
    case valor2:
        // código para valor2
        break;
    default:
        // código si ninguna case coincide
}
```

- `expresión_entera` debe ser un entero o `enum`.
- Cada `case` compara igualdad contra constantes.
- El `break` evita el “fall-through” hacia el siguiente `case`.
- `default` es opcional, sirve como “cajón de catch-all”.

---

## 5.2 Bucles

Los bucles repiten un bloque mientras una condición se cumpla (o al menos una vez, en un `do...while`).

|Bucle|Condición evaluada|Sintaxis básica|
|---|---|---|
|for|antes de cada iteración|for(inicio; condición; incremento) { … }|
|while|antes de cada iteración|while(condición) { … }|
|do…while|al final de cada iteración|do { … } while(condición);|

### for

```c
for (int i = 0; i < 10; i++) {
    // se repite 10 veces con i = 0..9
}
```

- Ideal cuando conoces el número de iteraciones.
- `inicio` se ejecuta una vez, `condición` se comprueba antes de cada paso, `incremento` al final de cada iteración.

### while

```c
int n = 0;
while (n < 5) {
    // repite mientras n sea menor que 5
    n++;
}
```

- Útil si no sabes cuántas veces necesitarás iterar hasta ejecutar el cuerpo al menos cero veces.

### do...while

```c
int opc;
do {
    // ejecuta al menos una vez
    opc = leer_opcion();
} while (opc != 0);
```

- Garantiza una primera ejecución antes de verificar la condición.

---

## 5.3 Sentencias de salto

Controlan saltos abruptos dentro de bucles o funciones.

- **break**: sale del bucle o del `switch` más cercano.
- **continue**: salta directamente a la siguiente iteración del bucle.
- **return**: termina la ejecución de la función actual y opcionalmente devuelve un valor.

```c
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break;       // sale del for cuando i vale 5
    }
    if (i % 2 == 0) {
        continue;    // salta el resto del cuerpo si i es par
    }
    printf("%d\n", i);  // imprime solo números impares menores que 5
}

int suma(int a, int b) {
    return a + b;         // finaliza la función devolviendo a + b
}
```

---

# Gestión de errores con goto

Utilizar `goto` de forma controlada puede simplificar la limpieza de recursos cuando múltiples niveles de validaciones o asignaciones pueden fallar. La idea es saltar a una etiqueta de “limpieza” que libere memoria, cierre archivos y ejecute acciones finales antes de finalizar la función.

```c
#include <stdio.h>
#include <stdlib.h>

int procesar_archivo(const char *ruta) {
    FILE *f = fopen(ruta, "r");
    if (!f) goto error;

    char *buffer = malloc(1024);
    if (!buffer) goto cleanup_file;

    // Operaciones que pueden fallar...
    if (fread(buffer, 1, 1024, f) < 1024) goto cleanup_buffer;

    // Éxito
    free(buffer);
    fclose(f);
    return 0;

cleanup_buffer:
    free(buffer);
cleanup_file:
    fclose(f);
error:
    // Manejo de errores centralizado
    fprintf(stderr, "Error procesando %s\n", ruta);
    return -1;
}
```

Este patrón mantiene la lógica secuencial clara y concentra todas las liberaciones en un único bloque, evitando duplicar llamadas a `free` o `fclose` y reduciendo riesgos de fugas de memoria.

---

# Patrones de estado y máquinas de estados finitos

Las máquinas de estados finitos (FSM) modelan sistemas mediante un conjunto de estados y transiciones disparadas por eventos o condiciones. En C, la forma clásica usa un bucle infinito más un `switch` sobre una variable de estado:

```c
typedef enum { INICIO, LEER_SENSOR, PROCESAR_DATO, FIN } Estado;

void fsm_loop(void) {
    Estado estado = INICIO;
    int dato;

    while (1) {
        switch (estado) {
            case INICIO:
                // inicializar hardware
                estado = LEER_SENSOR;
                break;
            case LEER_SENSOR:
                dato = leer_sensor();
                estado = (dato < UMBRAL) ? PROCESAR_DATO : FIN;
                break;
            case PROCESAR_DATO:
                procesar(dato);
                estado = FIN;
                break;
            case FIN:
                return;
        }
    }
}
```

Cada iteración evalúa solo el caso actual. Con FSM grandes, el `switch-case` puede volverse pesado; una alternativa es usar un arreglo de punteros a funciones, acelerando la transición al llamar directamente a la función del estado siguiente.

---

# Técnicas de early-return para simplificar funciones largas

El patrón de “early-return” o “fail-fast” reduce la indentación y las comprobaciones anidadas al salir lo antes posible cuando falla una precondición. Esto hace el cuerpo principal de la función más claro y evita variables de control adicionales.

```c
int validar_usuario(const char *u, const char *p) {
    if (!u || !*u) return -1;    // usuario vacío
    if (!p || !*p) return -2;    // contraseña vacía
    if (strlen(u) > 20) return -3;

    // lógica principal sin más indentación
    return autenticar(u, p);
}
```

En muchos casos devolver antes simplifica el flujo de lectura y mejora la mantenibilidad, tal como recomiendan prácticas de Spartan Programming para reducción de la complejidad ciclomática. Mientras más cortas y especializadas sean las funciones, más efectivo resulta este enfoque.
