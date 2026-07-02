# 📊 Análisis de Correlación de Indicadores Comerciales – City Club

## 📌 Descripción del proyecto

Este proyecto tiene como objetivo identificar qué indicadores comerciales presentan una mayor asociación con los ingresos totales de los clubes City Club.

A través de técnicas de análisis exploratorio de datos (EDA), limpieza de información y análisis de correlación, se evaluó el comportamiento de variables clave relacionadas con membresías y productos complementarios para comprender cuáles tienen mayor relación con el desempeño comercial.

---

## 🎯 Objetivo de negocio

Determinar qué indicadores comerciales están más relacionados con la generación de ingresos para apoyar la toma de decisiones comerciales y enfocar esfuerzos en las actividades con mayor impacto potencial.

---

## 🗂️ Dataset

La información utilizada corresponde a registros diarios de operación de los clubes City Club entre los años **2024 y 2026**.

### Variables analizadas

| Variable | Descripción |
|-----------|-------------|
| Renovaciones | Renovaciones de membresía realizadas |
| Afiliaciones | Nuevas membresías vendidas |
| AD2 | Segundas adicionales |
| Premias Cant | Cantidad de productos Premias vendidos |
| Premias $ | Ingreso generado por productos Premias |
| Punto de Venta | Ventas realizadas en piso |
| Ingresos Totales | Suma de Punto de Venta + Premias |
| Club | Sucursal correspondiente |
| Fecha | Fecha del registro |

> Cada fila representa la operación de un club en un día específico.

---

# 🔍 Metodología

## 1. Exploración inicial de datos

Se realizó una revisión general de:

- Dimensiones del dataset
- Tipos de datos
- Estadísticos descriptivos
- Distribución de variables

---

## 2. Calidad de datos

### Valores faltantes

Se identificaron registros con información faltante.

#### Hallazgos

- La mayoría de los valores nulos pertenecían al club **Cordilleras**, sucursal que dejó de operar durante el periodo analizado.
- Algunos registros aislados correspondían a retrasos o ausencia de reportes enviados por determinados clubes.

### Decisión

Debido a que los registros incompletos representaban menos del 1% de la información total y el objetivo era realizar análisis de correlación, se optó por eliminarlos para garantizar consistencia estadística.

---

## 3. Corrección de anomalías

Se detectó un registro con valores negativos en:

- Premias Cant
- Premias $

Dado que dichos indicadores no pueden tomar valores negativos operativamente, se verificó el registro y se corrigió utilizando valores positivos.

---

# 📈 Análisis de Correlación Nacional

Se utilizó el coeficiente de correlación de Pearson para evaluar la relación entre los indicadores comerciales y los ingresos totales.

## Resultados principales

| Variable | Correlación con Ingresos |
|-----------|-------------------------:|
| Renovaciones | **0.884** |
| Afiliaciones | 0.597 |
| AD2 | 0.553 |
| Premias Cant | 0.458 |
| Duplicados | 0.387 |
| Premias $ | 0.483 |

---

## Hallazgo principal

Las **renovaciones** mostraron la asociación más fuerte con los ingresos totales, superando a todos los demás indicadores analizados.

Esto sugiere que la retención y renovación de socios desempeña un papel fundamental dentro del modelo de ingresos de la compañía.

---

# 📊 Visualizaciones

Se construyeron diferentes visualizaciones para validar los resultados obtenidos:

### Heatmap de correlación

Permite visualizar la intensidad de las relaciones entre todas las variables analizadas.

<img width="863" height="779" alt="image" src="https://github.com/user-attachments/assets/33269dc9-c25c-41c2-bb2f-3c4cfb52b0b0" />


### Scatterplots

Se analizaron las relaciones entre:

- Renovaciones vs Ingresos
<img width="598" height="453" alt="image" src="https://github.com/user-attachments/assets/29ce8009-4c34-461d-9300-562e8b4c03bd" />

- Afiliaciones vs Ingresos
<img width="605" height="453" alt="image" src="https://github.com/user-attachments/assets/67ca1de2-def0-40d2-aab4-99d610ef011b" />

- AD2 vs Ingresos
<img width="598" height="453" alt="image" src="https://github.com/user-attachments/assets/9f8f5892-0a05-4bff-ab4f-242704311f1b" />

Los gráficos mostraron una tendencia positiva en todos los casos, siendo renovaciones la variable con el patrón más consistente.

---

# 🏢 Análisis por Club

Posteriormente se evaluó la hipótesis de que las diferencias de tamaño entre clubes podían influir en los resultados nacionales.

Para ello se agregaron los indicadores por sucursal.

## Correlaciones entre clubes

| Variable | Correlación con Ingresos |
|-----------|-------------------------:|
| Renovaciones | **0.968** |
| AD2 | 0.845 |
| Afiliaciones | 0.712 |
| Premias Cant | 0.491 |

---

## Hallazgo

Las correlaciones aumentan significativamente al analizar los datos por club.

Esto indica que parte de la variabilidad observada a nivel nacional está influenciada por diferencias estructurales entre sucursales.

En otras palabras, los clubes con mayor volumen de operación concentran una proporción importante de los ingresos totales.

---

# 🔎 Comparación entre clubes

Se seleccionaron clubes de diferentes tamaños para validar si el comportamiento era consistente:

| Tipo | Club |
|--------|--------|
| Grande | Nuevo Laredo |
| Mediano | Monclova |
| Pequeño | Santa Mónica |

### Resultados observados

- Las renovaciones mantuvieron una fuerte asociación con los ingresos en los distintos tamaños de club.
- La importancia relativa de afiliaciones, AD2 y Premias varió entre sucursales.
- Esto confirma que existen diferencias operativas entre clubes que merecen análisis específicos.

---

# 💡 Conclusiones

### Conclusión 1

Las renovaciones son el indicador con mayor asociación a los ingresos totales tanto a nivel nacional como a nivel sucursal.

### Conclusión 2

Las diferencias entre clubes tienen un efecto importante sobre los resultados agregados.

### Conclusión 3

Analizar únicamente el desempeño nacional puede ocultar comportamientos particulares de algunas sucursales.

### Conclusión 4

Los análisis futuros deberían profundizar en segmentaciones por:

- Club
- Región
- Año

Siendo el análisis por club la prioridad debido a su potencial para explicar diferencias estructurales en el desempeño comercial.

---

# 🚀 Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

# ▶️ Cómo ejecutar el proyecto

1. Clonar el repositorio.

```bash
git clone https://github.com/tu_usuario/analisis-correlacion-cityclub.git
```

2. Instalar dependencias.

```bash
pip install pandas numpy matplotlib seaborn
```

3. Abrir Jupyter Notebook.

```bash
jupyter notebook
```

4. Ejecutar el archivo:

```bash
Analisis_Correlacion_CityClub.ipynb
```

---

# 👨‍💻 Autor

**Humberto**

Proyecto desarrollado como práctica de análisis de datos aplicado a un caso real de negocio utilizando Python y técnicas de análisis exploratorio y correlacional.
