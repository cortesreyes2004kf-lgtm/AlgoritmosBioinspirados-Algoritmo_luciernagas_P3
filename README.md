# AlgoritmosBioinspirados-Algoritmo_luciernagas_P3

Este repositorio contiene la implementación y análisis comparativo del **Algoritmo de las Luciérnagas (Firefly Algorithm - FA)** aplicado a la resolución de problemas de optimización mono-objetivo. El trabajo forma parte de la asignatura de Algoritmos Bioinspirados y compara el desempeño del algoritmo propuesto frente a paradigmas evolutivos clásicos como el Algoritmo Genético (GA), Estrategias Evolutivas (EE) y Evolución Diferencial (ED).

## Información Institucional

* **Institución:** Instituto Politécnico Nacional (IPN) - Escuela Superior de Cómputo (ESCOM)
* **Docente:** Dra. Miriam Pescador Rojas
* **Integrantes:**
  * Arcia Portillo Héctor
  * Cortés Reyes Karla Fátima
  * Castro Luna Diego Francisco

---

## Estructura de los cuadernos

El proyecto está dividido en cuadernos secuenciales que documentan la evolución del algoritmo y las pruebas estadísticas:

1. **`1_Luciérnagas_AP_CL_CR.ipynb`**
   * Contiene la implementación base de los algoritmos evolutivos clásicos (GA, EE y DE) utilizando el framework `pymoo` para resolver las funciones de benchmark: Ackley, Griewank, Rastrigin y Rosenbrock. Así como el primer algoritmo clásico de luciérnagas adaptado a los parámetros de la práctica 3.

2. **`2_Comparación_de_funciones_con_FA.ipynb`**
   * Realiza la comparación estadística mediante la prueba de rangos con signo de Wilcoxon entre las soluciones obtenidas por el Algoritmo de las Luciérnagas estándar y los mejores resultados previos de la Práctica 3.

3. **`3_30_ejecuciones_y_adaptativo_1_5.ipynb`**
   * Incorpora un esquema de adaptación dinámica del parámetro de aleatoriedad ($\alpha$) en línea utilizando la **Regla de 1/5 de éxito**, ajustando la exploración y explotación según la tasa de mejora generacional.

4. **`4_Criterio_de_autoadaptacion_diseñado_para_FA.ipynb`**
   * Diseña y evalúa un criterio de autoadaptación propio para el Algoritmo de las Luciérnagas, alterando de forma dinámica tanto la aleatoriedad ($\alpha$) como la absorción lumínica ($\gamma$) en función de la tasa de éxito (Success Rate - SR).

5. **`5_Super_FA_adaptativo_.ipynb`**
   * Presenta la versión híbrida avanzada denominada **gbest-FA**. Integra decaimiento agresivo en momentos de estancamiento, uso de ruido Gaussiano en lugar de uniforme para mejorar la precisión y un componente de atracción hacia el líder global (gbest) inspirado en optimización por enjambre de partículas (PSO).

6. **`Ejecución_muestra.ipynb`**
   * Un entorno de prueba unificado para ejecutar el algoritmo propuesto sobre las diferentes funciones de prueba, generar visualizaciones en 3D del paisaje de búsqueda y aplicar la prueba estadística de Mann-Whitney U.

---

## Funciones Benchmark Evaluadas

La robustez de los algoritmos se evalúa bajo problemas de optimización de 10 dimensiones ($D = 10$) utilizando las siguientes funciones:
* **Ackley** (Límites: $[-32.768, 32.768]$)
* **Griewank** (Límites: $[-600, 600]$)
* **Rastrigin** (Límites: $[-5.12, 5.12]$)
* **Rosenbrock** (Límites: $[-2.048, 2.048]$)

---

## Metodología y Mejoras Propuestas

Para reducir la convergencia prematura en mínimos locales y mejorar la precisión en valles estrechos, se desarrollaron tres variantes adaptativas principales sobre el algoritmo clásico de Xin-She Yang:

1. **Ruido Gaussiano:** Sustituye el ruido uniforme clásico por una distribución normal, facilitando la convergencia al centro y una mejor aproximación al óptimo global.
2. **Atracción al Líder (gbest-FA):** Introduce un componente que atrae a la población hacia el mejor individuo de la generación actual, reduciendo la dispersión excesiva.
3. **Decaimiento Dinámico de Parámetros:** Ajusta los valores de exploración ($\alpha$) y explotación ($\gamma$) de acuerdo con la tasa de éxito generacional, disminuyendo la aleatoriedad a escalas milimétricas cuando el enjambre se encuentra en zonas de alta densidad de soluciones.

---

## Requisitos de Instalación

Para ejecutar los cuadernos de trabajo localmente, clone el repositorio e instale las dependencias especificadas en el archivo de requerimientos:

```bash
pip install -r requeriments.txt
