Te explico **Álgebra Lineal** desde los conceptos básicos hasta aplicaciones clave:

## 🔹 **Conceptos Fundamentales**

### **Vectores**
- **Definición**: Magnitud con dirección y sentido (en ℝ², ℝ³, etc.)
- **Representación**: `v = (x, y)` o `v = [x, y, z]ᵀ`
- **Operaciones básicas**:
  - Suma: `u + v = (u₁+v₁, u₂+v₂)`
  - Producto por escalar: `α·v = (α·v₁, α·v₂)`
  - Producto punto: `u·v = u₁v₁ + u₂v₂ + ...`
  - Norma/magnitud: `||v|| = √(v·v)`

### **Matrices**
- **Arreglo rectangular de números**
- **Notación**: A ∈ ℝᵐˣⁿ (m filas, n columnas)
- **Tipos importantes**:
  - Matriz identidad (I)
  - Matriz diagonal
  - Matriz simétrica (A = Aᵀ)
  - Matriz inversible (∃ A⁻¹)

## 🔹 **Operaciones con Matrices**

### **Multiplicación de Matrices**
```
C = A·B donde cᵢⱼ = Σ aᵢₖ·bₖⱼ
```
- **No es conmutativa**: A·B ≠ B·A (en general)
- **Dimensiones**: Aᵐˣⁿ · Bⁿᵖ = Cᵐˣᵖ

### **Transposición**
- Intercambiar filas por columnas
- (A·B)ᵀ = Bᵀ·Aᵀ

### **Traza**
- Suma de elementos diagonales: tr(A) = Σ aᵢᵢ

## 🔹 **Conceptos Avanzados**

### **Determinantes**
- **Scalar que indica "volumen"** de transformación
- **Propiedades**:
  - $det(I) = 1$
  - $det(A·B) = det(A)·det(B)$
  - $det(A⁻¹) = 1/det(A)$

### **Sistemas de Ecuaciones Lineales**
```
A·x = b
```
- **Solución única** si $det(A) ≠ 0$
- **Métodos de solución**: Eliminación Gaussiana, Regla de Cramer

### **Espacios Vectoriales**
- Conjunto de vectores con operaciones de suma y multiplicación por escalar
- **Subespacios**: Subconjuntos que también son espacios vectoriales

## 🔹 **Valores y Vectores Propios**

### **Definición**
```
A·v = λ·v
```
- **v**: vector propio (distinto de cero)
- **λ**: valor propio (escalar)

### **Aplicaciones**:
- Diagonalización de matrices
- Análisis de sistemas dinámicos
- Descomposición espectral

## 🔹 **Transformaciones Lineales**

### **Definición**
Función T: V → W que preserva:
- $T(u + v) = T(u) + T(v)$
- $T(α·v) = α·T(v)$

### **Matriz de Transformación**
Toda transformación lineal puede representarse como multiplicación por matriz

### **Tipos importantes**:
- **Rotaciones**
- **Reflexiones**
- **Escalamientos**
- **Proyecciones**

## 🔹 **Aplicaciones Prácticas**

### **En Ciencias de Computación**:
- Gráficos 3D y computación gráfica
- Machine Learning (PCA, SVD)
- Análisis de datos
- Criptografía

### **En Física**:
- Mecánica cuántica
- Relatividad
- Electromagnetismo

## 🔹 **Ejemplo Práctico: Rotación 2D**

```python
import numpy as np

# Matriz de rotación (30 grados)
theta = np.radians(30)
R = np.array([[np.cos(theta), -np.sin(theta)],
              [np.sin(theta), np.cos(theta)]])

# Vector original
v = np.array([1, 0])

# Vector rotado
v_rotado = R @ v
print(f"Vector rotado: {v_rotado}")
```

---
Te explico **Álgebra Lineal** con ejemplos en **C**:

## 🔹 **Estructuras Básicas**

### **Vector en 2D**
```c
typedef struct {
    float x;
    float y;
} Vector2D;

typedef struct {
    float x;
    float y;
    float z;
} Vector3D;
```

### **Matriz 2x2 y 3x3**
```c
typedef struct {
    float m[2][2];
} Matriz2x2;

typedef struct {
    float m[3][3];
} Matriz3x3;
```

## 🔹 **Operaciones con Vectores**

### **Suma de Vectores 2D**
```c
Vector2D suma_vectores(Vector2D a, Vector2D b) {
    Vector2D resultado;
    resultado.x = a.x + b.x;
    resultado.y = a.y + b.y;
    return resultado;
}
```

### **Producto Punto**
```c
float producto_punto(Vector2D a, Vector2D b) {
    return a.x * b.x + a.y * b.y;
}

// Uso:
Vector2D v1 = {2.0f, 3.0f};
Vector2D v2 = {1.0f, 4.0f};
float resultado = producto_punto(v1, v2); // 2*1 + 3*4 = 14
```

### **Magnitud de Vector**
```c
#include <math.h>

float magnitud(Vector2D v) {
    return sqrtf(v.x * v.x + v.y * v.y);
}
```

## 🔹 **Operaciones con Matrices**

### **Multiplicación Matriz 2x2**
```c
Matriz2x2 multiplicar_matrices(Matriz2x2 a, Matriz2x2 b) {
    Matriz2x2 resultado;
    
    resultado.m[0][0] = a.m[0][0]*b.m[0][0] + a.m[0][1]*b.m[1][0];
    resultado.m[0][1] = a.m[0][0]*b.m[0][1] + a.m[0][1]*b.m[1][1];
    
    resultado.m[1][0] = a.m[1][0]*b.m[0][0] + a.m[1][1]*b.m[1][0];
    resultado.m[1][1] = a.m[1][0]*b.m[0][1] + a.m[1][1]*b.m[1][1];
    
    return resultado;
}
```

### **Matriz Identidad 3x3**
```c
Matriz3x3 matriz_identidad() {
    Matriz3x3 id = {0};
    id.m[0][0] = 1.0f;
    id.m[1][1] = 1.0f;
    id.m[2][2] = 1.0f;
    return id;
}
```

## 🔹 **Transformaciones Lineales**

### **Matriz de Rotación 2D**
```c
#include <math.h>

Matriz2x2 matriz_rotacion(float angulo_rad) {
    Matriz2x2 rot;
    float cos_theta = cosf(angulo_rad);
    float sin_theta = sinf(angulo_rad);
    
    rot.m[0][0] = cos_theta;
    rot.m[0][1] = -sin_theta;
    rot.m[1][0] = sin_theta;
    rot.m[1][1] = cos_theta;
    
    return rot;
}
```

### **Aplicar Transformación a Vector**
```c
Vector2D aplicar_transformacion(Matriz2x2 m, Vector2D v) {
    Vector2D resultado;
    resultado.x = m.m[0][0]*v.x + m.m[0][1]*v.y;
    resultado.y = m.m[1][0]*v.x + m.m[1][1]*v.y;
    return resultado;
}
```

### **Ejemplo: Rotar Vector 45 grados**
```c
#include <stdio.h>
#include <math.h>

int main() {
    // Vector original
    Vector2D v = {1.0f, 0.0f};
    printf("Vector original: (%.2f, %.2f)\n", v.x, v.y);
    
    // Crear matriz de rotación (45 grados)
    float angulo = M_PI / 4.0f; // 45° en radianes
    Matriz2x2 rot = matriz_rotacion(angulo);
    
    // Aplicar rotación
    Vector2D v_rotado = aplicar_transformacion(rot, v);
    printf("Vector rotado: (%.2f, %.2f)\n", v_rotado.x, v_rotado.y);
    
    return 0;
}
```

## 🔹 **Sistema de Ecuaciones Lineales**

### **Eliminación Gaussiana para 2x2**
```c
typedef struct {
    float a, b, c; // ax + by = c
} Ecuacion;

void resolver_sistema_2x2(Ecuacion eq1, Ecuacion eq2, float *x, float *y) {
    float det = eq1.a * eq2.b - eq1.b * eq2.a;
    
    if (fabsf(det) < 1e-6) {
        printf("Sistema singular o sin solución única\n");
        *x = *y = 0.0f;
        return;
    }
    
    *x = (eq1.c * eq2.b - eq1.b * eq2.c) / det;
    *y = (eq1.a * eq2.c - eq1.c * eq2.a) / det;
}

// Uso:
Ecuacion eq1 = {2.0f, 3.0f, 5.0f}; // 2x + 3y = 5
Ecuacion eq2 = {1.0f, -1.0f, 1.0f}; // x - y = 1
float x, y;
resolver_sistema_2x2(eq1, eq2, &x, &y);
printf("Solución: x = %.2f, y = %.2f\n", x, y);
```

## 🔹 **Determinante y Matriz Inversa**

### **Determinante 2x2**
```c
float determinante_2x2(Matriz2x2 m) {
    return m.m[0][0] * m.m[1][1] - m.m[0][1] * m.m[1][0];
}
```

### **Matriz Inversa 2x2**
```c
Matriz2x2 inversa_2x2(Matriz2x2 m) {
    float det = determinante_2x2(m);
    Matriz2x2 inv;
    
    if (fabsf(det) < 1e-6) {
        printf("Matriz singular, no tiene inversa\n");
        return matriz_identidad_2x2();
    }
    
    inv.m[0][0] = m.m[1][1] / det;
    inv.m[0][1] = -m.m[0][1] / det;
    inv.m[1][0] = -m.m[1][0] / det;
    inv.m[1][1] = m.m[0][0] / det;
    
    return inv;
}

Matriz2x2 matriz_identidad_2x2() {
    Matriz2x2 id = {0};
    id.m[0][0] = 1.0f;
    id.m[1][1] = 1.0f;
    return id;
}
```

## 🔹 **Ejemplo Completo: Transformaciones**
```c
#include <stdio.h>
#include <math.h>

int main() {
    // Crear vector
    Vector2D punto = {2.0f, 3.0f};
    
    // Matriz de escala
    Matriz2x2 escala = {0};
    escala.m[0][0] = 2.0f; // Escala 2x en X
    escala.m[1][1] = 0.5f; // Escala 0.5x en Y
    
    // Aplicar transformación
    Vector2D punto_escalado = aplicar_transformacion(escala, punto);
    printf("Punto escalado: (%.2f, %.2f)\n", punto_escalado.x, punto_escalado.y);
    
    return 0;
}
```

---
(otro concepto por si no entiendes lo anterior)

# Álgebra Lineal: Conceptos Básicos

---

## Vectores

Un vector en ℝⁿ es una entidad que combina magnitud y dirección, representada como una tupla ordenada de n elementos. Se denota comúnmente **v** = (v₁, v₂, …, vₙ) y puede visualizarse como una flecha en el espacio.

Operaciones fundamentales con vectores:

- Suma: $u + v = (u₁+v₁, u₂+v₂, …, uₙ+vₙ)$
- Multiplicación escalar: $α·v = (α·v₁, α·v₂, …, α·vₙ)$
- Producto punto: $u·v = ∑ᵢ uᵢ·vᵢ$
- Norma (longitud): $‖v‖ = √(v·v)$

---

## Matrices

Una matriz A de tamaño m×n es un arreglo bidimensional de números aᵢⱼ dispuestos en m filas y n columnas. Se usa para representar transformaciones entre espacios vectoriales.

Operaciones principales:

- Suma/resta: $(A ± B)ᵢⱼ = aᵢⱼ ± bᵢⱼ$
- Multiplicación escalar: $(αA)ᵢⱼ = α·aᵢⱼ$
- Producto de matrices: $(AB)ᵢₖ = ∑ⱼ aᵢⱼ·bⱼₖ$
- Transpuesta: $(Aᵀ)ᵢⱼ = aⱼᵢ$
- Inversa (si A es cuadrada e invertible): $A⁻¹·A = I$

La **identidad** Iₙ satisface $Iₙ·A = A·Iₙ = A$, y el **determinante** det(A) mide el factor de escala y orientación de la transformación asociada.

---

## Transformaciones Lineales

Una transformación lineal $T: ℝⁿ → ℝᵐ$ cumple $T(u + v) = T(u) + T(v) y T(α·v) = α·T(v)$

Representación matricial:  
T(**x**) = A·**x**,  
donde A ∊ ℝᵐˣⁿ codifica la acción sobre la base canónica.

Ejemplos en ℝ²:

- Escalado:  
    $S(sₓ,sᵧ) = \begin{pmatrix} sₓ & 0 \ 0 & sᵧ \end{pmatrix}$
- Rotación de ángulo θ:  
    $R(θ) = \begin{pmatrix} \cos θ & -\sin θ \ \sin θ & \cos θ \end{pmatrix}$
- Reflexión, cizallamiento y proyección: otras transformaciones lineales habituales.

---
