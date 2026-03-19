# Proyecto de Estadística: Análisis de la Tasa de Paro Juvenil por Sexo

**Autor:** Ignacio Prim  
**Fecha:** 15 de marzo de 2026  
**Formato de análisis:** R Markdown (HTML)

## 📖 Descripción

Este proyecto realiza un análisis estadístico exhaustivo de la **tasa de paro juvenil en España**, utilizando datos desagregados por sexo (mujeres, varones y ambos sexos). El objetivo principal es describir el comportamiento de la variable, evaluar su representatividad, estudiar la relación entre la tasa de paro y el sexo, y finalmente construir un modelo de regresión lineal que explique la tasa global a partir de las tasas segregadas.

El análisis incluye:
- Estadísticos descriptivos (media geométrica, desviación típica, coeficiente de variación, mediana).
- Visualizaciones (diagrama de caja y nubes de puntos).
- Medidas de relación (covarianza, coeficiente V de Cramer).
- Modelo de regresión lineal múltiple y validación de residuos.

## 📁 Estructura del repositorio

| Archivo | Descripción |
|--------|-------------|
| `Proyecto_estadistica.Rmd` | Archivo principal en R Markdown que contiene todo el código, los comentarios y el análisis detallado. |
| `tablas_ambos_sexos_depurada.xlsx` | Datos depurados de la tasa de paro juvenil para el conjunto de la población (ambos sexos). |
| `tablas_mujeres_depurada.xlsx` | Datos depurados de la tasa de paro juvenil exclusivamente para mujeres. |
| `tablas_Varones_depurada.xlsx` | Datos depurados de la tasa de paro juvenil exclusivamente para varones. |
| `README.md` | Este archivo, con la descripción del proyecto y los resultados principales. |

## 🎯 Objetivos

1. **Describir** la tasa de paro juvenil en España mediante estadísticos robustos y gráficos.
2. **Comparar** las tasas de paro entre mujeres y varones, identificando posibles diferencias.
3. **Evaluar** la relación lineal entre las tasas segregadas y la tasa global.
4. **Construir** un modelo de regresión lineal que explique la tasa de paro total a partir de las tasas por sexo.
5. **Validar** la idoneidad del modelo mediante análisis de residuos.

## 🔬 Metodología y resultados clave

### 1. Análisis descriptivo

- **Media geométrica** (tasa de paro juvenil):
  - Mujeres: `0.149`
  - Varones: `0.157`
  - Ambos sexos: `0.152`
  > Se observa que la tasa media de paro en varones es aproximadamente un **5% superior** a la de mujeres.

- **Desviación típica** y **coeficiente de variación** (CV):
  - Mujeres: `sd = 0.022`, `CV = 0.148`
  - Varones: `sd = 0.030`, `CV = 0.191`
  - Ambos sexos: `sd = 0.026`, `CV = 0.168`
  > Los coeficientes de variación son bajos (inferiores a 0.2), lo que indica que las medias son **altamente representativas**.

- **Boxplot** de la tasa para ambos sexos:
  - Distribución **simétrica** y **concentrada** alrededor de la mediana.
  - Se identifican **dos valores atípicos** (probablemente correspondientes a Ceuta y Melilla).
  - La **mediana** (`0.1538`) es prácticamente idéntica a la media (`0.1546`), confirmando la simetría de los datos.

### 2. Relación entre sexo y tasa de paro

- **Gráficos de dispersión**:
  - Existe una **fuerte relación lineal** entre la tasa global y las tasas segregadas, con la excepción de los dos puntos atípicos.

- **Covarianza**:
  - Con mujeres: `0.00056`
  - Con varones: `0.00078`
  > Los valores positivos indican una relación directa.

- **Coeficiente V de Cramer** (correlación):
  - Con mujeres: `0.965`
  - Con varones: `1.000` (correlación perfecta)
  > La asociación entre las variables es **extremadamente alta**.

### 3. Modelo de regresión lineal

Se ajustó un modelo de regresión lineal múltiple:

\[
\text{Tasa ambos sexos} = \beta_0 + \beta_1 \cdot \text{Tasa mujeres} + \beta_2 \cdot \text{Tasa varones} + \varepsilon
\]

- **Análisis de residuos**:
  - Los residuos se distribuyen de forma **aleatoria**, sin patrones evidentes (ni curvas ni oscilaciones).
  - Esto confirma que el modelo **lineal es adecuado** para los datos.

## 💻 Requisitos y ejecución

Para reproducir el análisis necesitas:

- **R** (versión 4.0 o superior) y **RStudio** (recomendado).
- Paquetes de R:
  - `readxl` (para importar los datos Excel)
  - `DescTools` (para `Gmean`, `CoefVar`, `CramerV`)
  - `stats` (incluido por defecto para `lm`, `sd`, `cov`, `median`)

### Instrucciones

1. Clona este repositorio o descarga los archivos.
2. Abre `Proyecto_estadistica.Rmd` en RStudio.
3. Asegúrate de que los archivos Excel estén en el mismo directorio que el `.Rmd`.
4. Ejecuta las chunks de código de forma interactiva o haz clic en **Knit** para generar el informe completo en HTML.

## 📌 Conclusiones finales

- La tasa de paro juvenil en España se distribuye de forma **simétrica** y **concentrada** en torno al **15.4%**.
- Existe una **diferencia significativa** entre sexos: los varones presentan una tasa media **un 5% superior** a la de las mujeres.
- La relación entre las tasas por sexo y la tasa global es **prácticamente lineal y perfecta**, lo que permite predecir con gran exactitud la tasa total a partir de las segregadas.
- El modelo de regresión lineal es **válido y robusto**, como lo demuestra la aleatoriedad de los residuos.


## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Puedes usarlo, modificarlo y distribuirlo libremente, siempre que se cite la fuente original.

---
⌨️ Proyecto desarrollado con R por Ignacio Prim.
