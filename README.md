# Generación Solar Fotovoltaica en Colombia — Métodos Numéricos y Optimización

Análisis del recurso solar y modelado de generación fotovoltaica en distintas regiones de Colombia a partir de series meteorológicas horarias (NASA POWER), aplicando técnicas de limpieza/interpolación de datos, integración numérica, búsqueda de punto de máxima potencia ($V_{mp}$) y optimización.

> **Repositorio:** [Neyder2502/Energia-Solar-FV-Colombia](https://github.com/Neyder2502/Energia-Solar-FV-Colombia)

## Tabla de Contenidos

1. [Descripción General](#descripción-general)
2. [Ciudades y Fuente de Datos](#ciudades-y-fuente-de-datos)
3. [Metodología y Métodos Numéricos](#metodología-y-métodos-numéricos)
4. [Estructura del Repositorio](#estructura-del-repositorio)
5. [Ejecución](#ejecución)
6. [Resultados y Conclusiones](#resultados-y-conclusiones)

## Descripción General

Este proyecto evalúa el comportamiento de la irradiación solar, la temperatura de celda y la generación eléctrica fotovoltaica a lo largo del año en ciudades representativas de Colombia. El flujo de trabajo combina preprocesamiento de series temporales con métodos numéricos y de optimización para comparar el potencial energético entre ubicaciones y condiciones operativas.

## Ciudades y Fuente de Datos

- **Fuente:** Datos horarios de **NASA POWER** (irradiancia solar, temperatura ambiente, velocidad del viento, etc., a lo largo de un año completo = 8,760 registros horarios por ciudad).
- **Ciudades analizadas:**
  - **Riohacha**
  - **Valledupar**
  - **Medellín**
  - **Bogotá**
  - **Leticia**

## Metodología y Métodos Numéricos

1. **Limpieza y preprocesamiento:** Detección y tratamiento de valores faltantes o atípicos (como códigos `-999`), validación de rangos físicos y rellenado/interpolación de series horarias.
2. **Modelo térmico y eléctrico FV:** Estimación de la temperatura de celda (p. ej., modelo tipo NOCT) y potencia/generación fotovoltaica en función de la irradiancia y temperatura.
3. **Integración numérica:** Cálculo de energía/irradiación acumulada a partir de perfiles horarios o continuos mediante métodos como regla del trapecio, regla de Simpson, cuadratura/Romberg u otros esquemas implementados en el cuaderno.
4. **Optimización y ecuaciones no lineales:** Búsqueda del punto de operación / punto de máxima potencia ($V_{mp}$) y resolución de modelos mediante métodos numéricos / de optimización (por ejemplo: búsqueda de raíces / Newton, sección dorada, interpolación parabólica, formulación analítica/Lambert o programación lineal con `PuLP`).


## Estructura del Repositorio

```text
Energia-Solar-FV-Colombia/
├── README.md
├── Energia_Solar_FV_Colombia.pptx
├── Proyecto_final_metodos.ipynb
├── datos_csv.zip 
├── resultados
```

## Ejecución

### Opción A: Google Colab
1. Abre el cuaderno principal (`.ipynb`) en **Google Colab**.
2. Carga los archivos CSV correspondientes (o permite la descarga/lectura configurada en el cuaderno).
3. Ejecuta las celdas en orden de arriba hacia abajo.

### Opción B: Entorno Local
1. Asegúrate de tener instaladas las librerías de `requirements.txt`.
2. Abre Jupyter Notebook / JupyterLab / VS Code o ejecuta los scripts desde `src/` según corresponda.

## Resultados y Conclusiones

- **Comparación regional:** Contraste del recurso solar y la generación estimada entre regiones costeras/caribeñas, valles/montaña andina y Amazonía a lo largo del año y entre meses clave (por ejemplo, enero vs. julio).
- **Variabilidad:** Análisis de estacionalidad y variabilidad diaria/horaria del recurso solar.
- **Desempeño de métodos:** Comparación práctica de precisión, estabilidad y costo computacional entre los métodos numéricos y de optimización empleados.

## Autor

**Neyder Fabián Peña González** 
