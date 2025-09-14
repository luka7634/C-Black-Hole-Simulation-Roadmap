Te explico **Cálculo Diferencial e Integral** desde los conceptos básicos:

## 🔹 **LÍMITES Y CONTINUIDAD**

### **Concepto de Límite**
El límite describe el comportamiento de una función cuando se acerca a un punto:
```
lim f(x) = L
x→a
```

### **Continuidad**
Una función es continua en un punto si:
1. f(a) existe
2. lim f(x) existe
3. lim f(x) = f(a)
x→a

## 🔹 **DERIVADAS**

### **Definición Formal**
La derivada representa la **razón de cambio instantánea**:
$$
f'(x) = lim [f(x + h) - f(x)]/h
        h→0
$$

### **Interpretación Geométrica**
- **Pendiente de la recta tangente**
- **Velocidad instantánea** en física

### **Reglas de Derivación**
1. **Regla de la potencia**: $d/dx[xⁿ] = n·xⁿ⁻¹$
2. **Regla de la suma**: $d/dx[f + g] = f' + g'$
3. **Regla del producto**: $d/dx[f·g] = f'·g + f·g'$
4. **Regla del cociente**: $d/dx[f/g] = (f'·g - f·g')/g²$
5. **Regla de la cadena**: $d/dx[f(g(x))] = f'(g(x))·g'(x)$

## 🔹 **APLICACIONES DE DERIVADAS**

### **Máximos y Mínimos**
- **Puntos críticos**: donde f'(x) = 0 o f'(x) no existe
- **Criterio de la primera derivada**
- **Criterio de la segunda derivada**

### **Optimización**
Problemas de maximizar o minimizar funciones

## 🔹 **INTEGRALES**

### **Integral Indefinida**
Antiderivada: $∫f(x)dx = F(x) + C$ donde $F'(x) = f(x)$

### **Integral Definida**
```
∫[a,b] f(x)dx = Área bajo la curva
```

### **Teorema Fundamental del Cálculo**
```
∫[a,b] f(x)dx = F(b) - F(a)
```

## 🔹 **TÉCNICAS DE INTEGRACIÓN**

### **Métodos Comunes**
1. **Integración por sustitución**
2. **Integración por partes**: $∫u dv = uv - ∫v du$
3. **Integración por fracciones parciales**
4. **Sustitución trigonométrica**

## 🔹 **APLICACIONES DE INTEGRALES**

### **Áreas y Volúmenes**
- Área entre curvas
- Volúmenes de sólidos de revolución

### **Aplicaciones Físicas**
- Trabajo
- Centro de masa
- Longitud de arco

## 🔹 **SERIES Y SUCESIONES**

### **Series de Taylor**
Aproximación de funciones mediante polinomios:
```
f(x) = f(a) + f'(a)(x-a) + f''(a)(x-a)²/2! + ...
```

### **Convergencia**
- Criterio de la razón
- Criterio de la integral
- Criterio de comparación

## 🔹 **ECUACIONES DIFERENCIALES**

### **Ecuaciones Diferenciales Ordinarias**
Ecuaciones que involucran derivadas de una función

### **Métodos de Solución**
- Separación de variables
- Factor integrante
- Ecuaciones lineales

---
# Cálculo Diferencial e Integral con Ejemplos en C

## 🔹 **LÍMITES Y CONTINUIDAD**

### **Cálculo de Límites**
```c
#include <stdio.h>
#include <math.h>

// Función para calcular límite: f(x) = (sin x)/x cuando x→0
double calcular_limite_sinc() {
    double h = 1e-10;
    return sin(h) / h;  // Debería ser ≈1
}

// Límite de f(x) = (x² - 1)/(x - 1) cuando x→1
double limite_funcion_racional(double x) {
    if (fabs(x - 1.0) < 1e-10) {
        return 2.0;  // Por factorización: (x-1)(x+1)/(x-1) = x+1
    }
    return (x*x - 1.0) / (x - 1.0);
}

void demostrar_limites() {
    printf("Límite sin(x)/x cuando x→0: %.8f\n", calcular_limite_sinc());
    
    double valores[] = {0.999, 0.9999, 1.0001, 1.001};
    for (int i = 0; i < 4; i++) {
        printf("f(%.6f) = %.6f\n", valores[i], 
               limite_funcion_racional(valores[i]));
    }
}
```

## 🔹 **DERIVADAS - IMPLEMENTACIÓN EN C**

### **Derivada Numérica**
```c
// Derivada por diferencia central (más precisa)
double derivada(double (*f)(double), double x, double h) {
    return (f(x + h) - f(x - h)) / (2 * h);
}

// Derivada por diferencia hacia adelante
double derivada_adelante(double (*f)(double), double x, double h) {
    return (f(x + h) - f(x)) / h;
}

// Funciones de ejemplo
double funcion_cuadratica(double x) {
    return x * x;
}

double funcion_seno(double x) {
    return sin(x);
}

double funcion_exponencial(double x) {
    return exp(x);
}
```

### **Calculadora de Derivadas**
```c
void calcular_derivadas() {
    double x = 2.0;
    double h = 1e-5;
    
    printf("DERIVADAS EN x = %.2f:\n", x);
    printf("f(x) = x²: f'(%.2f) = %.6f (teórico: %.1f)\n", 
           x, derivada(funcion_cuadratica, x, h), 2*x);
    
    printf("f(x) = sin(x): f'(%.2f) = %.6f (teórico: %.6f)\n", 
           x, derivada(funcion_seno, x, h), cos(x));
    
    printf("f(x) = exp(x): f'(%.2f) = %.6f (teórico: %.6f)\n", 
           x, derivada(funcion_exponencial, x, h), exp(x));
}
```

## 🔹 **INTEGRACIÓN NUMÉRICA**

### **Método del Trapecio**
```c
double integrar_trapecio(double (*f)(double), double a, double b, int n) {
    double h = (b - a) / n;
    double suma = 0.5 * (f(a) + f(b));
    
    for (int i = 1; i < n; i++) {
        double x = a + i * h;
        suma += f(x);
    }
    
    return suma * h;
}
```

### **Método de Simpson**
```c
double integrar_simpson(double (*f)(double), double a, double b, int n) {
    if (n % 2 != 0) n++;  // n debe ser par
    double h = (b - a) / n;
    double suma = f(a) + f(b);
    
    for (int i = 1; i < n; i++) {
        double x = a + i * h;
        if (i % 2 == 0) {
            suma += 2 * f(x);
        } else {
            suma += 4 * f(x);
        }
    }
    
    return suma * h / 3;
}
```

### **Comparación de Métodos de Integración**
```c
void comparar_integracion() {
    double a = 0.0, b = M_PI;
    int n = 1000;
    
    // ∫sin(x)dx de 0 a π = 2
    double trapecio = integrar_trapecio(sin, a, b, n);
    double simpson = integrar_simpson(sin, a, b, n);
    
    printf("∫sin(x)dx de 0 a π:\n");
    printf("Método del Trapecio: %.8f (error: %.8f)\n", 
           trapecio, fabs(trapecio - 2.0));
    printf("Método de Simpson: %.8f (error: %.8f)\n", 
           simpson, fabs(simpson - 2.0));
}
```

## 🔹 **ECUACIONES DIFERENCIALES**

### **Método de Euler**
```c
void euler(double (*f)(double, double), double x0, double y0, 
           double x_final, int n) {
    double h = (x_final - x0) / n;
    double x = x0;
    double y = y0;
    
    printf("Método de Euler para dy/dx = f(x,y):\n");
    printf("x\t\ty\n");
    printf("%.6f\t%.6f\n", x, y);
    
    for (int i = 0; i < n; i++) {
        y = y + h * f(x, y);
        x = x + h;
        printf("%.6f\t%.6f\n", x, y);
    }
}

// Ejemplo: dy/dx = x + y
double ecuacion_diferencial_ejemplo(double x, double y) {
    return x + y;
}
```

### **Método de Runge-Kutta (Orden 4)**
```c
void runge_kutta_4(double (*f)(double, double), double x0, double y0, 
                   double x_final, int n) {
    double h = (x_final - x0) / n;
    double x = x0;
    double y = y0;
    
    printf("Método Runge-Kutta 4:\n");
    printf("x\t\ty\n");
    printf("%.6f\t%.6f\n", x, y);
    
    for (int i = 0; i < n; i++) {
        double k1 = h * f(x, y);
        double k2 = h * f(x + h/2, y + k1/2);
        double k3 = h * f(x + h/2, y + k2/2);
        double k4 = h * f(x + h, y + k3);
        
        y = y + (k1 + 2*k2 + 2*k3 + k4) / 6;
        x = x + h;
        printf("%.6f\t%.6f\n", x, y);
    }
}
```

## 🔹 **SERIES DE TAYLOR**

### **Aproximación de eˣ**
```c
double exp_taylor(double x, int n_terminos) {
    double resultado = 1.0;
    double termino = 1.0;
    
    for (int i = 1; i <= n_terminos; i++) {
        termino *= x / i;
        resultado += termino;
    }
    
    return resultado;
}

void comparar_exp_taylor() {
    double x = 1.0;
    int terminos = 10;
    
    printf("Aproximación de e^%.1f:\n", x);
    printf("Serie de Taylor (%d términos): %.8f\n", 
           terminos, exp_taylor(x, terminos));
    printf("Valor real (exp()): %.8f\n", exp(x));
}
```

### **Aproximación de sin(x)**
```c
double sin_taylor(double x, int n_terminos) {
    double resultado = 0.0;
    double termino = x;
    int signo = 1;
    
    for (int i = 1; i <= n_terminos; i += 2) {
        resultado += signo * termino;
        termino *= (x * x) / ((i + 1) * (i + 2));
        signo *= -1;
    }
    
    return resultado;
}
```

## 🔹 **PROGRAMA PRINCIPAL**
```c
int main() {
    printf("=== CÁLCULO CON C ===\n\n");
    
    // Límites
    printf("1. LÍMITES:\n");
    demostrar_limites();
    printf("\n");
    
    // Derivadas
    printf("2. DERIVADAS:\n");
    calcular_derivadas();
    printf("\n");
    
    // Integración
    printf("3. INTEGRACIÓN NUMÉRICA:\n");
    comparar_integracion();
    printf("\n");
    
    // Series de Taylor
    printf("4. SERIES DE TAYLOR:\n");
    comparar_exp_taylor();
    printf("\n");
    
    // Ecuaciones diferenciales
    printf("5. ECUACIONES DIFERENCIALES:\n");
    printf("dy/dx = x + y, y(0) = 1, x en [0, 1]\n");
    euler(ecuacion_diferencial_ejemplo, 0.0, 1.0, 1.0, 10);
    
    return 0;
}
```

## 🔹 **COMPILACIÓN Y EJECUACIÓN**
```bash
# Compilar con math library
gcc calculo.c -o calculo -lm

# Ejecutar
./calculo
```

Este código te permite:
- Calcular límites y derivadas numéricamente
- Integrar funciones usando diferentes métodos
- Resolver ecuaciones diferenciales
- Aproximar funciones con series de Taylor