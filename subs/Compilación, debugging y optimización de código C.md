## Compilación con GCC y Makefiles

Antes de generar un ejecutable necesitas compilar tu código en uno o varios objetos y luego enlazarlos. Con GCC, la invocación mínima es:

```bash
gcc -std=c11 -Wall -Wextra -pedantic -g -O0 archivo.c -o programa
```

- `-std=c11` especifica el estándar C.
- `-Wall -Wextra -pedantic` activan advertencias útiles.
- `-g` genera símbolos de depuración.
- `-O0` desactiva optimizaciones para compilaciones destinadas a debugging.

Para proyectos con varios archivos, un Makefile permite compilación incremental:

```makefile
CC = gcc
CFLAGS = -std=c11 -Wall -Wextra -pedantic -g -O0
SRC = src/a.c src/b.c
OBJ = $(SRC:.c=.o)

programa: $(OBJ)
    $(CC) $(OBJ) -o $@
```

---

## Debugging con GDB y símbolos optimizados

Para depurar en GDB de manera fiable:

- Compila con `-g` y evita optimizaciones agresivas (`-O0` o `-Og`).
- Usa `break`, `step`, `next` y `print` para inspeccionar flujo y variables.
- Si habilitas optimizaciones (`-O2`, `-O3`), el código puede reorganizarse, eliminar variables o inlinear funciones, dificultando el mapeo a la fuente. Para mitigar esto en entornos Visual Studio existe la opción `/Zo` para “Enhanced Optimized Debugging” que facilita la depuración de código optimizado conservando su rendimiento.

---

## Estrategias de optimización algorítmica

La base de un programa eficiente está en elegir algoritmos y estructuras de datos adecuados al problema. Cambiar de una lista enlazada a un arreglo puede reducir drásticamente el coste de acceso aleatorio, mientras que usar tablas hash en lugar de búsquedas lineales mejora tiempos de respuesta en colecciones grandes. Estas decisiones tienen un mayor impacto en el rendimiento que la mayoría de optimizaciones a nivel de código.

---

## Flags de optimización con GCC

GCC ofrece varios niveles de optimización:

|Flag|Descripción|
|---|---|
|-O0|Sin optimización (ideal para debugging).|
|-Og|Optimización ligera sin sacrificar la calidad de depuración.|
|-O2|Optimización equilibrada: inlining moderado, bucles, constantes.|
|-O3|Optimización agresiva: más inlining, vectorización y unrolling.|
|-Os|Optimiza para tamaño de código.|

Para maximizar rendimiento, añade:

- `-march=native` para generar código adaptado a la CPU local.
- `-funroll-loops` para desenrollar bucles críticos.
- `-flto` para optimización en tiempo de enlace.

Estos flags permiten al compilador invertir más recursos en el análisis estático y producir binarios más eficientes.

---

## Flujo recomendado

1. Durante desarrollo, compila con `-g -Og`.
2. Depura y corrige errores en GDB o con sanitizers (AddressSanitizer, Valgrind).
3. Para la versión de producción, recompila con `-O2 -march=native -flto`.
4. Mide el impacto con herramientas de profiling (gprof, perf) y ajusta algoritmos o flags según los cuellos de botella detectados.

---

Con este enfoque tienes un proceso claro: compilación modular con Makefile, debugging efectivo sin optimizaciones agresivas, y despliegue con las mejores opciones de GCC para maximizar el rendimiento.