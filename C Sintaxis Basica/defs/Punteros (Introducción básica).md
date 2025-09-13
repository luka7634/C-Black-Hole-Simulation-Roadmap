## ¿Qué es un puntero?

Un puntero es una variable cuyo valor es la dirección de memoria de otra variable. En lugar de almacenar directamente un dato, guarda la “dirección” o ubicación donde ese dato reside, permitiendo acceder y manipular esa memoria de manera eficiente.

## Declaración y uso básico

Para declarar un puntero se antepone un asterisco (`*`) al nombre de la variable del tipo al que apunta:

```c
int    *p_entero;    // puntero a un entero
double *p_doble;     // puntero a un double
char   *p_char;      // puntero a un char
```

Una vez declarado, se le asigna la dirección de una variable existente:

```c
int valor    = 42;
int *p_entero = &valor;  // p_entero apunta a la dirección de 'valor'
```

Tras la asignación, `p_entero` contiene la dirección de `valor` y puede usarse para leer o modificar su contenido.

## Operador de dirección (`&`) y de desreferenciación (`*`)

- `&` (operador de dirección): obtiene la dirección de memoria de una variable.
- `*` (operador de desreferenciación): accede o modifica el valor almacenado en la dirección apuntada por el puntero.

```c
int x = 100;
int *p = &x;      // p recibe la dirección de x

printf("Dirección de x: %p\n", (void*)p);  
printf("Valor de x: %d\n", *p);  // desreferencia para obtener 100

*p = 200;        // modifica x indirectamente
printf("Nuevo valor de x: %d\n", x);  // imprime 200
```

## Punteros y arreglos

En C, el nombre de un arreglo se comporta como un puntero constante a su primer elemento. Esto permite recorrerlo con aritmética de punteros:

```c
int nums[5] = {10, 20, 30, 40, 50};
int *p = nums;   // equivalente a &nums[0]

for (int i = 0; i < 5; i++) {
    printf("%d ", *(p + i));  // accede a nums[i]
}
```

También se puede avanzar o retroceder el puntero directamente:

```c
p++;   // ahora apunta a nums[1]
printf("%d\n", *p);  // imprime 20
```

