## Principios de la Programación Modular

La programación modular divide tu aplicación en piezas independientes (módulos), cada una con una responsabilidad clara. Un módulo suele constar de un fichero de cabecera (`.h`) que exporta la interfaz, y un fichero fuente (`.c`) que contiene la implementación.

Las ventajas principales son:

- Compilación incremental: solo recompilas los módulos modificados.
- Legibilidad y mantenimiento: cada módulo es más pequeño y enfocado.
- Reutilización: puedes enlazar o compartir módulos entre proyectos diferentes.

---

## Organización de Archivos

Una convención típica de proyecto modular es:

```
project/
├─ include/          # Cabeceras públicas (.h)
│  └─ modulo.h
├─ src/              # Implementaciones (.c)
│  └─ modulo.c
├─ tests/            # Pruebas unitarias
└─ Makefile
```

En `modulo.h` declaras tus prototipos y tipos públicos; en `modulo.c` defines las funciones y datos privados al módulo.

---

## Encapsulación con Include Guards

Para evitar inclusiones múltiples en la fase de preprocesado, añade “guards” en cada header:

```c
#ifndef MODULO_H
#define MODULO_H

/* declaracion de funciones y tipos */

#endif /* MODULO_H */
```

También puedes usar `#pragma once`, pero los guards tradicionales garantizan portabilidad máxima.

---

## Makefile y Compilación Incremental

Un Makefile simple para tu módulo podría ser:

```makefile
CC      := gcc
CFLAGS  := -Iinclude -Wall -Wextra -O2
SRC     := src/modulo.c
OBJ     := $(SRC:.c=.o)
LIB     := libmodulo.a

$(LIB): $(OBJ)
    ar rcs $@ $^

src/%.o: src/%.c
    $(CC) $(CFLAGS) -c $< -o $@

.PHONY: clean
clean:
    rm -f src/*.o $(LIB)
```

De este modo, tras cambiar `modulo.c`, solo recompilarás ese objeto y recrearás la librería estática.

---

## Buenas Prácticas de Código

- Nombres significativos: evita `aux1`, `tmp`; usa `buffer_size`, `compute_sum()`.
- Funciones con responsabilidad única: cada función debe hacer solo una tarea y tener un nombre que lo describa.
- Evita `goto` salvo en limpieza de recursos (patrón error/cleanup).
- Comentarios claros y commits descriptivos; documenta el “por qué”, no el “qué”.
- Limita la profundidad de anidamiento; prefiere early-return para validaciones.
- Usa `static` en funciones y variables internas para restringir el ámbito al módulo.

---

## Documentación y Herramientas

- Doxygen: documenta prototipos en comentarios para generar HTML o PDF.
- Linters (Splint, Cppcheck): detectan errores comunes, fugas de memoria y violaciones de estilo.
- Formateadores (clang-format): mantienen un estilo uniforme en todo el equipo.

Ejemplo de cabecera Doxygen:

```c
/**
 * @brief Calcula el factorial de n.
 * @param n Número entero >= 0
 * @return factorial de n, o -1 en caso de error
 */
long ml_factorial(int n);
```

---

## Ámbito y Visibilidad

- Variables globales: evítalas; si las necesitas, agrúpalas en un módulo y decláralas `static` en el `.c` para no exportarlas.
- Prototipos públicos en headers; funciones auxiliares (`static`) en la implementación.
- Esto minimiza dependencias y reduce superficies de acoplamiento entre módulos.

---

Con estas pautas tendrás un código en C estructurado, mantenible y fácil de escalar.
