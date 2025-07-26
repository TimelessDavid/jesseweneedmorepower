# Teoría de Diodos de Potencia

## 1. Introducción

Los diodos de potencia son dispositivos semiconductores diseñados para manejar corrientes y tensiones significativamente mayores que los diodos de señal. Se utilizan en fuentes de alimentación conmutadas, rectificadores de alta corriente y circuitos de protección contra sobrecargas. Según Rashid, su robustez y fiabilidad los hacen esenciales en sistemas de conversión de energía. Mohan et al. destacan su papel en el control de corrientes en convertidores AC–DC y DC–DC de potencia media y alta.

---

## 2. Estructura y Principio de Funcionamiento

La construcción interna de un diodo de potencia consiste en una unión PN con:
- Región P fuertemente dopada.
- Región N ligeramente dopada, para soportar tensiones elevadas.

Bajo polarización directa, la barrera de potencial disminuye y los portadores mayoritarios inyectados cruzan la unión, generando corriente \(I_D\). En polarización inversa se expande la zona de agotamiento hasta alcanzar la tensión de ruptura \(V_{BR}\) y producir avalancha controlada.

---

## 3. Características Eléctricas

### 3.1 Curva Corriente–Tensión (I–V)

La curva típica I–V de un diodo de potencia muestra:
- Región de polarización directa con caída de tensión umbral \(V_f\).
- Corriente de fuga inversa \(I_R\) muy baja hasta \(V_{BR}\).

### 3.2 Parámetros Clave

| Parámetro           | Símbolo   | Descripción                                           |
|---------------------|-----------|-------------------------------------------------------|
| Caída en conducción | \(V_f\)   | Tensión directa típica 0.7–1.5 V                     |
| Corriente inversa   | \(I_R\)   | Fuga en inversa, normalmente < µA                     |
| Tensión de ruptura  | \(V_{BR}\)| Máxima tensión soportada en inversa                  |
| Resistencia dinámica| \(r_d\)   | Derivada \(\frac{dV}{dI}\) en la región de conducción|

Rashid explica que \(V_f\) aumenta ligeramente con la corriente debido al efecto de resistencia serie interna. Mohan et al. añaden que \(I_R\) depende fuertemente de la temperatura de la unión.

---

## 4. Características de Conmutación

La recuperación inversa está determinada por la carga almacenada en la unión. Los parámetros críticos son:

| Tipo                 | \(t_{rr}\) (µs) | \(Q_{rr}\) (µC) |
|----------------------|-----------------|-----------------|
| Standard             | 2–5             | 20–100          |
| Recuperación rápida  | 0.5–2           | 5–20            |
| Ultrarrápido         | 0.05–0.5        | < 5             |

El valor de \(t_{rr}\) y \(Q_{rr}\) define la velocidad máxima de conmutación. Rashid ofrece ecuaciones para estimar \(Q_{rr}\) en función de la pendiente de corriente durante el apagado.

---

## 5. Clasificación

- Diodos standard de recuperación lenta  
- Diodos de recuperación rápida (Fast Recovery)  
- Diodos ultrarrápidos (Ultra Fast)  
- Diodos Schottky (sin almacenamiento de carga)

| Tipo        | Ventajas                           | Desventajas                |
|-------------|------------------------------------|----------------------------|
| Standard    | Bajo coste, alta robustez          | \(t_{rr}\) elevado         |
| Fast Recovery | Menor \(t_{rr}\), moderado coste | Ligera disipación extra    |
| Ultra Fast  | Muy alta velocidad de recuperación | Coste elevado, más frágil  |
| Schottky    | Caída \(V_f\) baja, sin \(Q_{rr}\) | \(V_{BR}\) limitada        |

---

## 6. Modelos Equivalentes

Un modelo simplificado incluye:
- Fuente ideal de tensión \(V_f\).  
- Resistencia serie \(R_s\).  
- Capacitancia de unión \(C_j(V)\), dependiente de polarización.

   ┌───┬───┐  
   │   │   ├─> \(I_D\)  
   │  \(R_s\) │  
   │   │   │  
──▶│|>|│   ├─┬─ \(C_j(V)\)  
   │   │   │ │  
   └───┴───┘ └─ GND  

Rashid discute cómo el modelado de \(C_j\) es clave para simular la conmutación rápida.

---

## 7. Consideraciones Térmicas

La potencia disipada en el diodo se calcula como:  


\[
P_D = V_f \cdot I_D
\]



Para asegurar \(T_j < T_{max}\), se selecciona un disipador con resistencia térmica \(\theta_{JA}\) adecuada y se evalúa:  


\[
\Delta T = P_D \times \theta_{JA} \quad;\quad T_j = T_{amb} + \Delta T
\]



Mohan et al. proporcionan métodos para estimar \(\theta_{JA}\) en función del encapsulado y el flujo de aire.

---

## 8. Aplicaciones Típicas

- Rectificación en fuentes AC–DC de alta potencia  
- Bobinado freewheeling en convertidores de motor  
- Protección frente a inversión de polaridad en baterías  
- Circuitos de recorte y clamp  

---

## 9. Ejemplo de Cálculo de Disipador

1. Datos: \(V_f = 1.0\)\,V, \(I_D = 20\)\,A  
2. Potencia: \(P_D = 1.0 \times 20 = 20\)\,W  
3. \(\theta_{JA} = 5\)\,°C/W, \(T_{amb} = 40\)\,°C  
4. \(\Delta T = 20 \times 5 = 100\)\,°C  
5. \(T_j = 40 + 100 = 140\)\,°C (< 150 °C)

---

## Bibliografía

- [1] Muhammad H. Rashid, *Power Electronics: Circuits, Devices and Applications*, 4ª ed., Pearson, 2018.  
- [2] Ned Mohan, Tore M. Undeland, William P. Robbins, *Power Electronics: Converters, Applications, and Design*, 3ª ed., Wiley, 2002.  
