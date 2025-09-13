## **1. CINEMÁTICA: Descripción del Movimiento**

### **1.1 Posición, Velocidad y Aceleración**

**Vector posición** en 3D:
$$\vec{r}(t) = x(t)\hat{i} + y(t)\hat{j} + z(t)\hat{k}$$

**Velocidad instantánea**:
$$\vec{v}(t) = \frac{d\vec{r}}{dt} = \frac{dx}{dt}\hat{i} + \frac{dy}{dt}\hat{j} + \frac{dz}{dt}\hat{k}$$

**Aceleración instantánea**:
$$\vec{a}(t) = \frac{d\vec{v}}{dt} = \frac{d^2\vec{r}}{dt^2} = \frac{d^2x}{dt^2}\hat{i} + \frac{d^2y}{dt^2}\hat{j} + \frac{d^2z}{dt^2}\hat{k}$$

### **1.2 Movimiento en Coordenadas Cartesianas**

**Ecuaciones paramétricas**:
$$x(t) = x_0 + v_{x0}t + \frac{1}{2}a_xt^2$$
$$y(t) = y_0 + v_{y0}t + \frac{1}{2}a_yt^2$$
$$z(t) = z_0 + v_{z0}t + \frac{1}{2}a_zt^2$$

### **1.3 Movimiento Circular**

**Posición angular**:
$$\theta(t) = \theta_0 + \omega_0 t + \frac{1}{2}\alpha t^2$$

**Relaciones lineales-angulares**:
$$v = \omega r$$
$$a_t = \alpha r$$
$$a_c = \frac{v^2}{r} = \omega^2 r$$

## 🔹 **2. DINÁMICA: Leyes de Newton**

### **2.1 Primera Ley (Ley de Inercia)**
$$\sum \vec{F} = 0 \Rightarrow \frac{d\vec{v}}{dt} = 0$$

### **2.2 Segunda Ley (F = ma)**
$$\sum \vec{F} = m\vec{a} = m\frac{d^2\vec{r}}{dt^2}$$

**Forma diferencial**:
$$\vec{F} = \frac{d\vec{p}}{dt} \quad \text{donde} \quad \vec{p} = m\vec{v}$$

### **2.3 Tercera Ley (Acción-Reacción)**
$$\vec{F}_{AB} = -\vec{F}_{BA}$$

## 🔹 **3. FUERZAS FUNDAMENTALES**

### **3.1 Fuerza Gravitacional**
**Ley de Gravitación Universal**:
$$\vec{F}_g = -G\frac{m_1 m_2}{r^2}\hat{r}$$

**Energía potencial gravitacional**:
$$U_g = -G\frac{m_1 m_2}{r}$$

### **3.2 Fuerza Elástica (Ley de Hooke)**
$$\vec{F}_e = -k\vec{x}$$

**Energía potencial elástica**:
$$U_e = \frac{1}{2}kx^2$$

### **3.3 Fuerza de Fricción**
**Fricción cinética**:
$$f_k = \mu_k N$$

**Fricción estática**:
$$f_s \leq \mu_s N$$

## 🔹 **4. TRABAJO Y ENERGÍA**

### **4.1 Trabajo Mecánico**
**Trabajo infinitesimal**:
$$dW = \vec{F} \cdot d\vec{r}$$

**Trabajo total**:
$$W = \int_C \vec{F} \cdot d\vec{r}$$

### **4.2 Teorema del Trabajo-Energía**
$$W_{\text{total}} = \Delta K = \frac{1}{2}mv_f^2 - \frac{1}{2}mv_i^2$$

### **4.3 Energía Mecánica Total**
$$E = K + U = \frac{1}{2}mv^2 + U(\vec{r})$$

### **4.4 Conservación de la Energía Mecánica**
Si $\vec{F} = -\nabla U$ (fuerza conservativa):
$$\Delta E = 0 \Rightarrow E_f = E_i$$

## 🔹 **5. MOMENTO LINEAL E IMPULSO**

### **5.1 Momento Lineal**
$$\vec{p} = m\vec{v}$$

### **5.2 Teorema del Impulso-Momento**
$$\vec{J} = \int_{t_i}^{t_f} \vec{F} dt = \Delta \vec{p}$$

### **5.3 Conservación del Momento Lineal**
Si $\sum \vec{F}_{\text{ext}} = 0$:
$$\frac{d\vec{p}_{\text{total}}}{dt} = 0 \Rightarrow \vec{p}_{\text{total}} = \text{constante}$$

## 🔹 **6. SISTEMAS DE PARTÍCULAS**

### **6.1 Centro de Masa**
$$\vec{R}_{\text{CM}} = \frac{1}{M_{\text{total}}} \sum_{i=1}^n m_i \vec{r}_i$$

**Para distribución continua**:
$$\vec{R}_{\text{CM}} = \frac{1}{M} \int \vec{r} dm$$

### **6.2 Movimiento del Centro de Masa**
$$\vec{F}_{\text{ext}} = M_{\text{total}} \vec{a}_{\text{CM}}$$

## 🔹 **7. ROTACIÓN DE CUERPOS RÍGIDOS**

### **7.1 Momento de Inercia**
$$I = \sum_i m_i r_i^2 \quad \text{o} \quad I = \int r^2 dm$$

### **7.2 Torque**
$$\vec{\tau} = \vec{r} \times \vec{F}$$

### **7.3 Segunda Ley para Rotación**
$$\sum \tau = I\alpha = I\frac{d^2\theta}{dt^2}$$

### **7.4 Momento Angular**
$$\vec{L} = \vec{r} \times \vec{p}$$

**Para rotación**:
$$\vec{L} = I\vec{\omega}$$

### **7.5 Conservación del Momento Angular**
Si $\sum \vec{\tau}_{\text{ext}} = 0$:
$$\frac{d\vec{L}}{dt} = 0 \Rightarrow \vec{L} = \text{constante}$$

## 🔹 **8. OSCILACIONES Y MOVIMIENTO ARMÓNICO**

### **8.1 Ecuación del Movimiento Armónico Simple**
$$\frac{d^2x}{dt^2} + \omega^2 x = 0 \quad \text{donde} \quad \omega = \sqrt{\frac{k}{m}}$$

### **8.2 Solución General**
$$x(t) = A\cos(\omega t + \phi)$$

**Velocidad y aceleración**:
$$v(t) = -A\omega\sin(\omega t + \phi)$$
$$a(t) = -A\omega^2\cos(\omega t + \phi)$$

## 🔹 **9. FORMULACIÓN LAGRANGIANA**

### **9.1 Coordenadas Generalizadas**
$$\vec{r}_i = \vec{r}_i(q_1, q_2, \ldots, q_n, t)$$

### **9.2 Lagrangiano**
$$\mathcal{L} = T - U$$

### **9.3 Ecuaciones de Euler-Lagrange**
$$\frac{d}{dt}\left(\frac{\partial\mathcal{L}}{\partial\dot{q}_i}\right) - \frac{\partial\mathcal{L}}{\partial q_i} = 0$$

## 🔹 **10. FORMULACIÓN HAMILTONIANA**

### **10.1 Momentos Generalizados**
$$p_i = \frac{\partial\mathcal{L}}{\partial\dot{q}_i}$$

### **10.2 Hamiltoniano**
$$\mathcal{H} = \sum_i p_i\dot{q}_i - \mathcal{L}$$

### **10.3 Ecuaciones de Hamilton**
$$\frac{dq_i}{dt} = \frac{\partial\mathcal{H}}{\partial p_i}, \quad \frac{dp_i}{dt} = -\frac{\partial\mathcal{H}}{\partial q_i}$$

## 🔹 **11. MOVIMIENTO EN CAMPOS CENTRALES**

### **11.1 Potencial Central**
$$U = U(r)$$

### **11.2 Conservación del Momento Angular**
$$\vec{L} = \vec{r} \times m\vec{v} = \text{constante}$$

### **11.3 Ecuación de la Órbita**
$$\frac{d^2u}{d\theta^2} + u = -\frac{m}{L^2}\frac{dU}{du} \quad \text{donde} \quad u = \frac{1}{r}$$

### **11.4 Órbitas Keplerianas**
**Para potencial gravitacional**:
$$r(\theta) = \frac{p}{1 + e\cos\theta}$$

**Donde**:
$$p = \frac{L^2}{Gm_1m_2\mu}, \quad e = \sqrt{1 + \frac{2EL^2}{\mu(Gm_1m_2)^2}}$$

## 🔹 **12. PRINCIPIOS VARIACIONALES**

### **12.1 Principio de Hamilton**
$$\delta \int_{t_1}^{t_2} \mathcal{L} dt = 0$$

### **12.2 Principio de Mínima Acción**
La trayectoria real minimiza la acción:
$$S = \int_{t_1}^{t_2} \mathcal{L} dt$$

## 🔹 **13. TEOREMAS DE CONSERVACIÓN**

### **13.1 Teorema de Noether**
A cada simetría continua del Lagrangiano le corresponde una cantidad conservada.

**Ejemplos**:
- Homogeneidad del tiempo → Conservación de la energía
- Homogeneidad del espacio → Conservación del momento lineal
- Isotropía del espacio → Conservación del momento angular

## 🔹 **14. ECUACIONES DE MOVIMIENTO EN DIFERENTES SISTEMAS**

### **14.1 Coordenadas Cilíndricas**
$$\vec{r} = \rho\hat{\rho} + z\hat{z}$$
$$\vec{v} = \dot{\rho}\hat{\rho} + \rho\dot{\phi}\hat{\phi} + \dot{z}\hat{z}$$
$$\vec{a} = (\ddot{\rho} - \rho\dot{\phi}^2)\hat{\rho} + (\rho\ddot{\phi} + 2\dot{\rho}\dot{\phi})\hat{\phi} + \ddot{z}\hat{z}$$

### **14.2 Coordenadas Esféricas**
$$\vec{r} = r\hat{r}$$
$$\vec{v} = \dot{r}\hat{r} + r\dot{\theta}\hat{\theta} + r\sin\theta\dot{\phi}\hat{\phi}$$
$$\vec{a} = (\ddot{r} - r\dot{\theta}^2 - r\sin^2\theta\dot{\phi}^2)\hat{r} + (r\ddot{\theta} + 2\dot{r}\dot{\theta} - r\sin\theta\cos\theta\dot{\phi}^2)\hat{\theta} + (r\sin\theta\ddot{\phi} + 2\dot{r}\sin\theta\dot{\phi} + 2r\cos\theta\dot{\theta}\dot{\phi})\hat{\phi}$$

## 🔹 **15. APLICACIONES AVANZADAS**

### **15.1 Problema de los Dos Cuerpos**
**Masa reducida**:
$$\mu = \frac{m_1 m_2}{m_1 + m_2}$$

**Movimiento relativo**:
$$\mu \frac{d^2\vec{r}}{dt^2} = \vec{F}_{12}$$

### **15.2 Dispersión Rutherford**
**Fórmula de dispersión**:
$$\frac{d\sigma}{d\Omega} = \left(\frac{Z_1Z_2e^2}{16\pi\epsilon_0E}\right)^2 \frac{1}{\sin^4(\theta/2)}$$

### **15.3 Pequeñas Oscilaciones**
**Matriz de masa y matriz de rigidez**:
$$T = \frac{1}{2}\sum_{i,j} M_{ij}\dot{q}_i\dot{q}_j, \quad U = \frac{1}{2}\sum_{i,j} K_{ij}q_iq_j$$

**Ecuación de autovalores**:
$$(K - \omega^2M)\vec{a} = 0$$

---

# Mecánica Clásica: Implementación en C

## 🔹 **1. ESTRUCTURAS BÁSICAS Y CINEMÁTICA**

```c
#include <stdio.h>
#include <math.h>
#include <stdlib.h>

#define G 6.67430e-11  // Constante gravitacional
#define PI 3.14159265358979323846

// Estructuras básicas
typedef struct {
    double x, y, z;
} Vector3D;

typedef struct {
    Vector3D posicion;
    Vector3D velocidad;
    Vector3D aceleracion;
    double masa;
} Particula;

// Operaciones vectoriales
Vector3D vector_suma(Vector3D a, Vector3D b) {
    return (Vector3D){a.x + b.x, a.y + b.y, a.z + b.z};
}

Vector3D vector_resta(Vector3D a, Vector3D b) {
    return (Vector3D){a.x - b.x, a.y - b.y, a.z - b.z};
}

Vector3D vector_escalar(Vector3D v, double s) {
    return (Vector3D){v.x * s, v.y * s, v.z * s};
}

double producto_punto(Vector3D a, Vector3D b) {
    return a.x*b.x + a.y*b.y + a.z*b.z;
}

double norma_vector(Vector3D v) {
    return sqrt(v.x*v.x + v.y*v.y + v.z*v.z);
}

Vector3D producto_cruz(Vector3D a, Vector3D b) {
    return (Vector3D){
        a.y*b.z - a.z*b.y,
        a.z*b.x - a.x*b.z,
        a.x*b.y - a.y*b.x
    };
}
```

## 🔹 **2. CINEMÁTICA - MOVIMIENTO PARABÓLICO**

```c
void movimiento_proyectil(double v0, double angulo_grados, double dt, double t_max) {
    double g = 9.81;
    double angulo_rad = angulo_grados * PI / 180.0;
    
    double vx = v0 * cos(angulo_rad);
    double vy = v0 * sin(angulo_rad);
    double x = 0, y = 0, t = 0;
    
    printf("Movimiento de Proyectil:\n");
    printf("Tiempo\tX\t\tY\t\tVx\t\tVy\n");
    
    while (t <= t_max && y >= 0) {
        printf("%.3f\t%.3f\t%.3f\t%.3f\t%.3f\n", t, x, y, vx, vy);
        
        // Integración de Euler
        x += vx * dt;
        y += vy * dt;
        vy -= g * dt;
        t += dt;
    }
}
```

## 🔹 **3. DINÁMICA - LEYES DE NEWTON**

```c
// Segunda Ley: F = ma
Vector3D calcular_aceleracion(Vector3D fuerza, double masa) {
    return vector_escalar(fuerza, 1.0/masa);
}

Vector3D calcular_fuerza(double masa, Vector3D aceleracion) {
    return vector_escalar(aceleracion, masa);
}

// Tercera Ley: Par acción-reacción
typedef struct {
    Vector3D fuerza_accion;
    Vector3D fuerza_reaccion;
    int id_cuerpo_a;
    int id_cuerpo_b;
} ParAccionReaccion;
```

## 🔹 **4. FUERZAS FUNDAMENTALES**

```c
// Fuerza Gravitacional
Vector3D fuerza_gravitacional(Particula a, Particula b) {
    Vector3D r = vector_resta(b.posicion, a.posicion);
    double distancia = norma_vector(r);
    
    if (distancia < 1e-10) return (Vector3D){0, 0, 0};
    
    Vector3D direccion = vector_escalar(r, 1.0/distancia);
    double magnitud = G * a.masa * b.masa / (distancia * distancia);
    
    return vector_escalar(direccion, magnitud);
}

// Fuerza Elástica (Ley de Hooke)
Vector3D fuerza_elastica(Vector3D posicion, Vector3D equilibrio, double k) {
    Vector3D desplazamiento = vector_resta(posicion, equilibrio);
    return vector_escalar(desplazamiento, -k);
}

// Fuerza de Fricción
Vector3D fuerza_friccion_cinetica(Vector3D velocidad, double mu, double normal) {
    if (norma_vector(velocidad) < 1e-10) 
        return (Vector3D){0, 0, 0};
    
    Vector3D direccion = vector_escalar(velocidad, -1.0/norma_vector(velocidad));
    return vector_escalar(direccion, mu * normal);
}
```

## 🔹 **5. ENERGÍA Y TRABAJO**

```c
// Energía Cinética
double energia_cinetica(Particula p) {
    double v2 = producto_punto(p.velocidad, p.velocidad);
    return 0.5 * p.masa * v2;
}

// Energía Potencial Gravitacional
double energia_potencial_gravitacional(Particula a, Particula b) {
    Vector3D r = vector_resta(b.posicion, a.posicion);
    double distancia = norma_vector(r);
    return -G * a.masa * b.masa / distancia;
}

// Energía Potencial Elástica
double energia_potencial_elastica(Vector3D pos, Vector3D eq, double k) {
    Vector3D despl = vector_resta(pos, eq);
    double dist2 = producto_punto(despl, despl);
    return 0.5 * k * dist2;
}

// Trabajo realizado por una fuerza
double calcular_trabajo(Vector3D fuerza, Vector3D desplazamiento) {
    return producto_punto(fuerza, desplazamiento);
}
```

## 🔹 **6. MOMENTO LINEAL Y COLISIONES**

```c
// Momento Lineal
Vector3D calcular_momento_lineal(Particula p) {
    return vector_escalar(p.velocidad, p.masa);
}

// Conservación del momento (sistema de dos partículas)
void colision_elastica_1d(Particula *a, Particula *b) {
    double m1 = a->masa, m2 = b->masa;
    double v1 = a->velocidad.x, v2 = b->velocidad.x;
    
    double v1f = ((m1 - m2)*v1 + 2*m2*v2) / (m1 + m2);
    double v2f = ((m2 - m1)*v2 + 2*m1*v1) / (m1 + m2);
    
    a->velocidad.x = v1f;
    b->velocidad.x = v2f;
}
```

## 🔹 **7. SISTEMAS DE PARTÍCULAS**

```c
// Centro de Masa
Vector3D centro_de_masa(Particula sistema[], int n) {
    Vector3D cm = {0, 0, 0};
    double masa_total = 0;
    
    for (int i = 0; i < n; i++) {
        cm.x += sistema[i].masa * sistema[i].posicion.x;
        cm.y += sistema[i].masa * sistema[i].posicion.y;
        cm.z += sistema[i].masa * sistema[i].posicion.z;
        masa_total += sistema[i].masa;
    }
    
    return vector_escalar(cm, 1.0/masa_total);
}
```

## 🔹 **8. ROTACIÓN Y MOMENTO ANGULAR**

```c
// Momento de Inercia (esfera sólida)
double momento_inercia_esfera(double masa, double radio) {
    return 0.4 * masa * radio * radio;
}

// Torque
Vector3D calcular_torque(Vector3D posicion, Vector3D fuerza) {
    return producto_cruz(posicion, fuerza);
}

// Momento Angular
Vector3D calcular_momento_angular(Particula p, Vector3D punto_referencia) {
    Vector3D r = vector_resta(p.posicion, punto_referencia);
    return producto_cruz(r, calcular_momento_lineal(p));
}
```

## 🔹 **9. MOVIMIENTO ARMÓNICO SIMPLE**

```c
void movimiento_armonico_simple(double A, double omega, double phi, double dt, double t_max) {
    double t = 0;
    printf("Movimiento Armónico Simple:\n");
    printf("Tiempo\tPosición\tVelocidad\tAceleración\n");
    
    while (t <= t_max) {
        double x = A * cos(omega * t + phi);
        double v = -A * omega * sin(omega * t + phi);
        double a = -A * omega * omega * cos(omega * t + phi);
        
        printf("%.3f\t%.3f\t%.3f\t%.3f\n", t, x, v, a);
        t += dt;
    }
}
```

## 🔹 **10. PROBLEMA DE DOS CUERPOS**

```c
void problema_dos_cuerpos(Particula *p1, Particula *p2, double dt, int pasos) {
    printf("Simulación de Dos Cuerpos:\n");
    
    for (int i = 0; i < pasos; i++) {
        // Calcular fuerza gravitacional
        Vector3D f12 = fuerza_gravitacional(*p1, *p2);
        Vector3D f21 = vector_escalar(f12, -1);
        
        // Actualizar aceleraciones
        p1->aceleracion = calcular_aceleracion(f12, p1->masa);
        p2->aceleracion = calcular_aceleracion(f21, p2->masa);
        
        // Integrar (Método de Euler)
        p1->velocidad = vector_suma(p1->velocidad, vector_escalar(p1->aceleracion, dt));
        p2->velocidad = vector_suma(p2->velocidad, vector_escalar(p2->aceleracion, dt));
        
        p1->posicion = vector_suma(p1->posicion, vector_escalar(p1->velocidad, dt));
        p2->posicion = vector_suma(p2->posicion, vector_escalar(p2->velocidad, dt));
        
        if (i % 100 == 0) {
            printf("Paso %d: Distancia = %.3f\n", i, 
                   norma_vector(vector_resta(p1->posicion, p2->posicion)));
        }
    }
}
```

## 🔹 **11. PROGRAMA PRINCIPAL**

```c
int main() {
    printf("=== MECÁNICA CLÁSICA EN C ===\n\n");
    
    // 1. Movimiento de proyectil
    printf("1. MOVIMIENTO DE PROYECTIL\n");
    movimiento_proyectil(50.0, 45.0, 0.1, 10.0);
    printf("\n");
    
    // 2. Problema de dos cuerpos
    printf("2. PROBLEMA DE DOS CUERPOS\n");
    Particula sol = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}, 1.989e30};
    Particula tierra = {{1.496e11, 0, 0}, {0, 2.978e4, 0}, {0, 0, 0}, 5.972e24};
    
    problema_dos_cuerpos(&sol, &tierra, 3600, 1000); // dt=1h, 1000 pasos
    printf("\n");
    
    // 3. Movimiento armónico simple
    printf("3. MOVIMIENTO ARMÓNICO SIMPLE\n");
    movimiento_armonico_simple(1.0, 2.0*PI, 0.0, 0.1, 2.0);
    printf("\n");
    
    // 4. Colisión elástica
    printf("4. COLISIÓN ELÁSTICA 1D\n");
    Particula a = {{0, 0, 0}, {2.0, 0, 0}, {0, 0, 0}, 1.0};
    Particula b = {{5.0, 0, 0}, {-1.0, 0, 0}, {0, 0, 0}, 2.0};
    
    printf("Antes: v1=%.1f, v2=%.1f\n", a.velocidad.x, b.velocidad.x);
    colision_elastica_1d(&a, &b);
    printf("Después: v1=%.1f, v2=%.1f\n", a.velocidad.x, b.velocidad.x);
    
    return 0;
}
```

## 🔹 **12. COMPILACIÓN**

```bash
gcc mecanica.c -o mecanica -lm
./mecanica
```

Este código implementa los conceptos fundamentales de la mecánica clásica:
- Cinemática y dinámica
- Leyes de Newton
- Fuerzas fundamentales
- Conservación de energía y momento
- Sistemas de partículas
- Movimiento armónico
- Problema de dos cuerpos

Cada sección incluye ejemplos prácticos y verificables de los principios físicos.