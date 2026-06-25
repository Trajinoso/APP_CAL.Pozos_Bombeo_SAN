
# Simulador de Grupos de Bombeo

## 1. Visión General

Esta herramienta web de ingeniería MEP ha sido desarrollada para facilitar el **pre-dimensionamiento y análisis de puntos de operación** en sistemas de bombeo centrífugo. Permite modelar el comportamiento hidráulico de conjuntos de bombas trabajando en configuraciones de serie o paralelo, evaluando su convergencia con la curva resistente de una instalación.

## 2. Fundamentos Técnicos y Modelado

El simulador utiliza un modelo cuadrático para aproximar las curvas características, basado en la teoría clásica de turbomáquinas centrífugas.

### Curva del Sistema (Resistencia)

Representa la pérdida de energía necesaria para mover un caudal ($Q$) a través de una red, considerando:

* **Altura Geométrica ($H_g$):** Diferencia de cota entre los espejos de agua.
* **Presión Residual ($P_{res}$):** Presión requerida en el punto de entrega.
* **Pérdidas de Carga ($H_f$):** Consideradas mediante la ecuación de Darcy-Weisbach simplificada, donde $H_f = K_{sys} \cdot Q^2$.

### Curva Característica de la Bomba

Se asume una curva de bomba de tipo **estable** (con pendiente negativa constante), descrita por la ecuación parabólica:
$H = H_0 - K_{pump} \cdot Q^2$
Donde $H_0$ es la altura a caudal cero (cierre) y $K_{pump}$ es el coeficiente de pérdida interna de la bomba.

## 3. Comportamiento del Grupo

El simulador permite visualizar el desplazamiento del punto de operación (intersección entre la curva de la bomba y la del sistema) bajo diferentes configuraciones:

| Configuración | Efecto Hidráulico | Aplicación Típica |
| --- | --- | --- |
| **Paralelo** | Aumenta el caudal ($Q$) manteniendo la altura ($H$) constante. | Sistemas con alta demanda de caudal.|
| **Serie** | Aumenta la altura ($H$) manteniendo el caudal ($Q$) constante. | Sistemas con grandes pérdidas de carga o altura geométrica elevada.|

## 4. Limitaciones del Modelo

Para garantizar un uso responsable de la herramienta, se debe considerar que este modelo es una aproximación:

* **No considera el punto de máxima eficiencia (BEP):** El simulador no calcula el rendimiento ($\eta$) ni la potencia absorbida ($P_{abs}$), por lo que no verifica si la bomba opera en su zona de eficiencia óptima.
* **Suposición de bombas idénticas:** Se asume que todas las bombas en serie o paralelo tienen características hidráulicas idénticas.
* **Cavitación (NPSH):** No se realiza una verificación de NPSH disponible vs. requerido; se recomienda validar esta condición mediante las curvas del fabricante antes de la selección final.

## 5. Instrucciones de Implementación

### Tecnologías

* **Motor:** JavaScript (Vanilla) para el cálculo matricial de intersecciones.

* **Gráficos:** *Chart.js* (v.3.x+).

* **Responsive:** CSS Grid y Media Queries para adaptabilidad en tablets/móviles.


### Despliegue

1. Clone el repositorio.
2. Abra el archivo `index.html` en un navegador compatible con ES6. No requiere servidor de aplicaciones ni dependencias de backend, ya que todas las operaciones son calculadas en el lado del cliente (Client-Side Rendering).

---

*Documentación técnica preparada para equipos de ingeniería MEP. Para dudas sobre la validez de los coeficientes $K_{sys}$, contactar con el departamento de proyectos.*

