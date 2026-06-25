# MEP-002 · Cálculo de Caudales (HVAC)

`MEP-002` es una aplicación web interactiva de código abierto diseñada para el **cálculo y dimensionado preliminar de caudales hidráulicos** en sistemas de climatización (HVAC). Permite configurar múltiples circuitos en paralelo (modos Frío y Calor) evaluando de forma dinámica las propiedades termofísicas del agua para estimar los diámetros nominales (DN) óptimos y la potencia hidráulica de bombeo requerida en el sistema.

---

## 🚀 Características Clave

* **Cómputo en Tiempo Real (Client-Side Puro):** Ejecución 100% local en el navegador mediante JavaScript Vanilla (ES6). No requiere servidores backend ni bases de datos.
* **Precisión Termofísica:** Ajuste dinámico de la densidad ($\rho$) y el calor específico ($C_p$) del agua en función de la temperatura media de cada circuito mediante ecuaciones polinómicas de alta fidelidad.
* **Dimensionado Orientativo (DN):** Sugerencia de Diámetro Nominal tanto para el colector/anillo principal (primario) como para las derivaciones individuales (secundarios) en base a velocidades de diseño objetivo.
* **Análisis de Estabilidad y Margen:** Monitoreo del ratio de bypass mínimo absoluto frente al caudal nominal y etiquetado de circuitos críticos.
* **Listo para Reportes:** Formato optimizado para impresión física o guardado en PDF (CSS `@print`), junto con una función nativa de exportación de datos en formato estructurado JSON.

---

## 🧮 Fundamentos Científicos y Fórmulas

La herramienta calcula el caudal volumétrico y de masa a partir del balance térmico fundamental en estado estacionario:

$$Q = \frac{P}{\rho(T_m) \cdot C_p(T_m) \cdot \Delta T}$$

Donde:

* $P$: Potencia térmica demandada por el circuito ($\text{kW}$).
* $T_m$: Temperatura media del circuito ($\frac{T_{ida} + T_{ret}}{2}$ en $^{\circ}\text{C}$).
* $\rho(T_m)$: Densidad del agua ($\text{kg/m}^3$) calculada dinámicamente mediante la **Ecuación de Kell** (rango operativo optimizado de $0\text{--}100\text{ }^{\circ}\text{C}$).
* $C_p(T_m)$: Capacidad calorífica específica del agua ($\text{kJ/kg}\cdot\text{K}$) evaluada mediante un polinomio cuadrático de regresión térmica.
* $\Delta T$: Salto térmico absoluto entre la impulsión y el retorno ($|T_{ida} - T_{ret}|$ en $\text{K}$).

### Estimación de la Potencia Hidráulica ($P_h$)

El consumo energético del bombeo en el punto de diseño se computa mediante la relación:

$$P_h = \frac{\rho_{nom} \cdot g \cdot Q_{total} \cdot H}{\eta \cdot 1000}$$

Donde $H$ es la altura manométrica ($\text{m c.a.}$), $\eta$ el rendimiento global de la bomba, $g \approx 9.81\text{ m/s}^2$ y $\rho_{nom} \approx 998\text{ kg/m}^3$.

---

## 🛠️ Tecnologías Utilizadas

* **Frontend:** HTML5, CSS3 (con soporte nativo para CSS Variables y maquetación responsiva a través de Flexbox y CSS Grid).
* **Motor Lógico:** JavaScript Vanilla (ES6) enfocado en cálculos matriciales por filas de circuitos.
* **Referencias Normativas (Informativas):** Criterios alineados bajo los parámetros generales de la directiva **RITE (IT 1.2.4.2)**, **UNE-EN 12828**, y el **CTE HE-2**.

---

## 💻 Instalación y Despliegue

Al no contar con dependencias externas ni compiladores (`Webpack`, `Vite`, etc.), el despliegue es inmediato:

1. Clonar el repositorio:
```bash
git clone https://github.com/tu-usuario/mep-002-calculo-caudales.git

```


2. Entrar al directorio del proyecto y abrir el archivo principal:
* Simplemente haz doble clic sobre el archivo `index.html` en cualquier navegador moderno (Edge, Chrome, Firefox, Safari).
* O puedes servirlo localmente mediante Python para pruebas rápidas:
```bash
python -m http.server 8080

```





---

## 📊 Formato de Exportación (JSON)

Al presionar el botón **"📋 Copiar"**, la aplicación genera una estructura limpia en el portapapeles para su fácil integración con otros software de diseño MEP o hojas de cálculo:

```json
{
  "id": "MEP-002",
  "version": "1.0.1",
  "global": {
    "H_mca": 15,
    "eta": 0.65,
    "v_sec_ms": 1.2,
    "v_pri_ms": 2,
    "Q_bypass_min_m3h": 20,
    "Q_total_m3h": 41.52
  },
  "circuits": [
    {
      "name": "Frío – UTA",
      "mode": "frio",
      "P_kW": 500,
      "Ti_C": 7,
      "Tr_C": 12,
      "dT_K": 5,
      "Tm_C": 9.5,
      "rho_kgm3": 999.78,
      "cp_kJkgK": 4.202,
      "Q_m3h": 85.69,
      "Q_ls": 23.80,
      "mdot_kgs": 23.79,
      "critico": true
    }
  ]
}

```

---

## ⚠️ Limitaciones del Modelo

> [!WARNING]
> * **Fluido base único:** Los cálculos consideran agua pura como fluido caloportador. Si tu sistema trabaja con mezclas de Glicol (Etileno/Propileno), las propiedades físicas ($\rho, C_p$) variarán incrementando los caudales y pérdidas reales.
> 
> 

* **Serie Comercial de Tuberías:** Las velocidades resultantes se asocian a diámetros interiores de referencia genéricos (`DN15` a `DN300`). Validar siempre con el catálogo del fabricante de tuberías seleccionado (PPR, Acero Negro, Multicapa, etc.).
* **Cavitación y Pérdidas de Carga:** El módulo calcula caudales y pre-dimensiona diámetros por velocidad límite; no evalúa pérdidas de carga lineales/singulares detalladas ni el NPSH requerido por el grupo de bombeo.
