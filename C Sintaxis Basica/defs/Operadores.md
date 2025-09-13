## Operadores aritméticos

Los operadores aritméticos realizan las operaciones matemáticas básicas entre operandos numéricos:

- `+` Suma de dos operandos.
- `-` Resta del segundo operando al primero.
- `*` Multiplicación de dos operandos.
- `/` División del primer operando entre el segundo.
- `%` Módulo o resto entero de la división (solo con tipos enteros).

Ejemplo:

```c
int a = 7, b = 3;
int suma     = a + b;   // 10
int resta    = a - b;   // 4
int mult     = a * b;   // 21
int divi     = a / b;   // 2  (división entera)
int modulo   = a % b;   // 1  (resto de la división)
```

Este operador módulo no puede aplicarse a `float` o `double`.

---

## Operadores relacionales

Los operadores relacionales comparan dos expresiones y devuelven 1 (verdadero) o 0 (falso):

- `==` Igualdad.
- `!=` Desigualdad.
- `<` Menor que.
- `>` Mayor que.
- `<=` Menor o igual que.
- `>=` Mayor o igual que.

Ejemplo:

```c
int x = 5, y = 8;
int eq  = (x == y);   // 0
int neq = (x != y);   // 1
int lt  = (x < y);    // 1
int gt  = (x > y);    // 0
```

Estas comparaciones son esenciales para estructuras de control como `if` y `while`.

---

## Operadores lógicos

Combinan o invierten valores booleanos (0 o distintos de cero):

- `&&` AND lógico: verdadero si ambas expresiones son verdaderas.
- `||` OR lógico: verdadero si al menos una expresión es verdadera.
- `!` NOT lógico: invierte el valor de la expresión.

Ejemplo:

```c
int a = 1, b = 0;
int and = (a && b);   // 0
int or  = (a || b);   // 1
int not = (!a);       // 0
```

Se usan para construir condiciones compuestas en controles de flujo.

---

## Operadores de asignación

Asignan valores o modifican la variable izquierda usando una operación con el operando derecho:

- `=` Asignación simple.
- `+=` Suma y asigna. Equivale a `x = x + y`.
- `-=` Resta y asigna. Equivale a `x = x - y`.
- `*=` Multiplica y asigna.
- `/=` Divide y asigna.
- `%=` Módulo y asigna.

Ejemplo:

```c
int n = 10;
n += 5;   // ahora vale 15
n -= 3;   // ahora vale 12
n *= 2;   // ahora vale 24
n /= 4;   // ahora vale 6
n %= 5;   // ahora vale 1
```

Estos operadores simplifican el código y evitan recalcular la variable en la expresión.

---

## Operadores bit a bit

Trabajan a nivel de bits sobre operandos enteros (`char`, `int`, `long`):

- `&` AND bit a bit.
- `|` OR bit a bit.
- `^` XOR bit a bit.
- `~` NOT bit a bit (complemento).
- `<<` Desplazamiento a la izquierda.
- `>>` Desplazamiento a la derecha.

Ejemplo:

```c
unsigned char u = 0b10110010;
unsigned char and = u & 0b11001100;   // 0b10000000
unsigned char or  = u | 0b01010101;   // 0b11110111
unsigned char xor = u ^ 0b11110000;   // 0b01000010
unsigned char not = ~u;               // 0b01001101
unsigned char shl = u << 2;           // 0b11001000
unsigned char shr = u >> 3;           // 0b00010110
```

Estos operadores son clave para enmascarar, habilitar y desplazar bits en operaciones de bajo nivel.

---

## Precedencia de operadores

El orden de evaluación (de mayor a menor prioridad) es:

1. Paréntesis `()`
2. Operadores unarios: `! ~ + - ++ --`
3. Multiplicación, división y módulo: `* / %`
4. Suma y resta: `+ -`
5. Desplazamientos: `<< >>`
6. Comparaciones relacionales: `< <= > >=`
7. Igualdad: `== !=`
8. AND bit a bit: `&`
9. XOR bit a bit: `^`
10. OR bit a bit: `|`
11. AND lógico: `&&`
12. OR lógico: `||`
13. Operadores de asignación: `= += -= ...`

Para forzar un orden distinto, usa paréntesis: todo lo que esté dentro de `()` se evalúa primero, independientemente de la precedencia estándar.# 4. Operadores en C

---

## Operadores aritméticos

Los operadores aritméticos realizan las operaciones matemáticas básicas entre operandos numéricos:

- `+` Suma de dos operandos.
- `-` Resta del segundo operando al primero.
- `*` Multiplicación de dos operandos.
- `/` División del primer operando entre el segundo.
- `%` Módulo o resto entero de la división (solo con tipos enteros).

Ejemplo:

```c
int a = 7, b = 3;
int suma     = a + b;   // 10
int resta    = a - b;   // 4
int mult     = a * b;   // 21
int divi     = a / b;   // 2  (división entera)
int modulo   = a % b;   // 1  (resto de la división)
```

Este operador módulo no puede aplicarse a `float` o `double`.

---

## Operadores relacionales

Los operadores relacionales comparan dos expresiones y devuelven 1 (verdadero) o 0 (falso):

- `==` Igualdad.
- `!=` Desigualdad.
- `<` Menor que.
- `>` Mayor que.
- `<=` Menor o igual que.
- `>=` Mayor o igual que.

Ejemplo:

```c
int x = 5, y = 8;
int eq  = (x == y);   // 0
int neq = (x != y);   // 1
int lt  = (x < y);    // 1
int gt  = (x > y);    // 0
```

Estas comparaciones son esenciales para estructuras de control como `if` y `while`.

---

## Operadores lógicos

Combinan o invierten valores booleanos (0 o distintos de cero):

- `&&` AND lógico: verdadero si ambas expresiones son verdaderas.
- `||` OR lógico: verdadero si al menos una expresión es verdadera.
- `!` NOT lógico: invierte el valor de la expresión.

Ejemplo:

```c
int a = 1, b = 0;
int and = (a && b);   // 0
int or  = (a || b);   // 1
int not = (!a);       // 0
```

Se usan para construir condiciones compuestas en controles de flujo.

---

## Operadores de asignación

Asignan valores o modifican la variable izquierda usando una operación con el operando derecho:

- `=` Asignación simple.
- `+=` Suma y asigna. Equivale a `x = x + y`.
- `-=` Resta y asigna. Equivale a `x = x - y`.
- `*=` Multiplica y asigna.
- `/=` Divide y asigna.
- `%=` Módulo y asigna.

Ejemplo:

```c
int n = 10;
n += 5;   // ahora vale 15
n -= 3;   // ahora vale 12
n *= 2;   // ahora vale 24
n /= 4;   // ahora vale 6
n %= 5;   // ahora vale 1
```

Estos operadores simplifican el código y evitan recalcular la variable en la expresión.

---

## Operadores bit a bit

Trabajan a nivel de bits sobre operandos enteros (`char`, `int`, `long`):

- `&` AND bit a bit.
- `|` OR bit a bit.
- `^` XOR bit a bit.
- `~` NOT bit a bit (complemento).
- `<<` Desplazamiento a la izquierda.
- `>>` Desplazamiento a la derecha.

Ejemplo:

```c
unsigned char u = 0b10110010;
unsigned char and = u & 0b11001100;   // 0b10000000
unsigned char or  = u | 0b01010101;   // 0b11110111
unsigned char xor = u ^ 0b11110000;   // 0b01000010
unsigned char not = ~u;               // 0b01001101
unsigned char shl = u << 2;           // 0b11001000
unsigned char shr = u >> 3;           // 0b00010110
```

Estos operadores son clave para enmascarar, habilitar y desplazar bits en operaciones de bajo nivel.

---

## Precedencia de operadores

El orden de evaluación (de mayor a menor prioridad) es:

1. Paréntesis `()`
2. Operadores unarios: `! ~ + - ++ --`
3. Multiplicación, división y módulo: `* / %`
4. Suma y resta: `+ -`
5. Desplazamientos: `<< >>`
6. Comparaciones relacionales: `< <= > >=`
7. Igualdad: `== !=`
8. AND bit a bit: `&`
9. XOR bit a bit: `^`
10. OR bit a bit: `|`
11. AND lógico: `&&`
12. OR lógico: `||`
13. Operadores de asignación: `= += -= ...`

Para forzar un orden distinto, usa paréntesis: todo lo que esté dentro de `()` se evalúa primero, independientemente de la precedencia estándar.