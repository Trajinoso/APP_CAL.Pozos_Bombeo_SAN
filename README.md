**Este es el archivo `README.md` principal (*root*) para el repositorio global de utilidades y aplicaciones MEP. Está estructurado de manera fucinal, sirviendo como índice unificado para los diferentes módulos que se van desarrollando.**

---
## 📂 Índice de Aplicaciones y Módulos

* [APP cálculo HS5: Pozo Bombeo Saneamiento ](./APP_1.Cal.PB_SAN/)
* [APP cálculo HS1: Pozo Bombeo Nivel Freático](./APP_2.Calc.PB_NF/)
* [APP Cálculo Curva Bombas](./APP_3.Calc_B.HID_Multiples/)
* [APP Cálculo Caudales AA para refrigeración](./APP_4.Calc.Caudales-AA/)
* [APP Cálculo Hidráulico Piscinas](./APP_5.Calc.HID_Piscinas/)
* [APP Cálculo Hidráulico Piscinas Full con información](./APP_5.1.Calc.HID_Piscina_Full/)
* [APP Cálculo SUA8: Necesidad Pararrayos](./APP_6.Calc.SUA8_Pararrayos/)
* [APP Cálculo Deshumectación Piscina](./APP_7.Calc.DESH_Piscina/)

---

# MEP & Hydraulic Engineering Suite

Este repositorio centraliza un conjunto de aplicaciones e instrumentos técnicos interactivos orientados al **cálculo, dimensionado preliminar y supervisión visual de instalaciones integrales**.

Todas las aplicaciones se ejecutan bajo una arquitectura **Client-Side pura (CSR)**, lo que garantiza privacidad absoluta de los datos, agilidad y despliegue inmediato sin dependencias de servidor ni bases de datos.

---

## 🛠️ Stack Tecnológico Común

Las herramientas de este ecosistema comparten una filosofía de desarrollo ágil y ligera:

* **Lógica Core:** JavaScript Vanilla (ES6+) sin frameworks ni sobrecargas de procesamiento. Cálculos deterministas y matrices estáticas de componentes comerciales.
* **UI/UX:** HTML5 semántico y CSS3 avanzado utilizando maquetaciones fluidas (`CSS Grid` / `Flexbox`) con sistemas de variables nativas para interfaces en Modo Oscuro de alta fidelidad.
* **Gráficos e Infografías:** Motores ligeros como `Chart.js` y `Mermaid.js` acoplados directamente en el flujo del cliente.
* **Reportes:** Directivas estricta de CSS `@media print` para la supresión de elementos interactivos de la UI en la generación de memorias técnicas en papel o PDF.

---

## 🚀 Despliegue Local Inmediato

Al no contar con dependencias de servidor ni procesos de compilación (`Webpack`, `Vite`, etc.), puedes ejecutar cualquiera de las herramientas de forma local:

1. Clonar el repositorio completo:
```bash
git clone https://github.com/tu-usuario/tu-repositorio-mep.git

```
2. Ejecutar directamente abriendo el archivo `.html` deseado en cualquier navegador moderno con soporte ES6.

---
