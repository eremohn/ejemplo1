# Análisis Exploratorio de Datos (EDA) - Restaurantes USA

## 📋 Descripción del Proyecto

Este proyecto realiza un análisis exploratorio completo de datos de clientes de restaurantes en Estados Unidos. El dataset contiene información de 30,000 clientes distribuidos en 10 ciudades principales, con variables demográficas, hábitos de consumo y preferencias de clientes.

**Objetivo**: Identificar patrones en el comportamiento de clientes, correlacionar variables clave y proporcionar insights accionables para optimizar estrategias de marketing, mejorar la retención y aumentar ingresos.

---

## 📊 Hallazgos Principales

### 1. **Distribución Geográfica**
- **Ciudades principales**: Miami, Denver, Boston, San Diego, Dallas, NYC, Seattle, Chicago, Houston, Phoenix.
- Denver y Miami concentran la mayor cantidad de clientes con perfiles de alto gasto.
- La distribución por ciudad correlaciona con oportunidades de expansión.

### 2. **Análisis de Nulos**
- **Teléfono**: 50.55% faltante (estrategia de comunicación digital necesaria).
- **Correo**: 50.24% faltante (similar necesidad).
- **Preferencias alimenticias**: 4.68% (requiere limpieza antes de análisis).
- **Edad y gasto**: Baja proporción de nulos (< 1%), datos confiables para modelado.

### 3. **Comportamiento de Clientes**
- **Gasto vs Ingresos**: Correlación positiva significativa.
- **Frecuencia vs Gasto**: Clientes con mayor frecuencia de visita gastan más.
- **Estrato socioeconómico**: Predictor fuerte del gasto promedio (Bajo < Medio < Alto).
- **Edad**: Clientes mayores (55+) tienen mayor frecuencia de visita pero gasto variable.

### 4. **Preferencias y Características**
- **Preferencias alimenticias**: Varían por ciudad (Vegetariano más en Seattle; Carnívoro en ciudades de Texas).
- **Membresía premium**: 40-50% de clientes con membresía según ciudad; correlaciona con gasto alto.
- **Consumo de alcohol**: Positivo en 65-70% de clientes; correlaciona con edad (disminuye con la edad).

### 5. **Integración de Datos Externos (Yelp)**
- **Rating promedio por ciudad**: 3.5-4.5 estrellas.
- **Correlación Rating-Gasto**: Ciudades con ratings más altos (>4.0) tienen clientes con 15-20% más gasto.
- **Frecuencia de visita**: Clientes en ciudades con ratings altos visitan 1.3x más frecuentemente.

### 6. **Segmentación de Clientes (K-Means, 4 Clusters)**
- **Cluster 0 - Jóvenes de Bajo Ingreso** (25%): Edad 20-35, ingresos $2,500-3,500/mes, gasto bajo.
- **Cluster 1 - Alto Ingreso/Alto Gasto** (15%): Edad 35-55, ingresos $6,000-8,000/mes, gasto $150-250/mes.
- **Cluster 2 - Mayores Frecuentes** (30%): Edad 50-75, ingresos $4,000-5,500/mes, gasto medio, frecuencia alta.
- **Cluster 3 - Ingreso Medio Balanceado** (30%): Edad 30-50, ingresos $4,000-5,500/mes, equilibrio gasto-frecuencia.

---

## 🔄 Proceso Realizado

### Fase 1: Carga y Limpieza (Celdas 1-7)
- Carga del CSV con encoding UTF-8.
- Detección de nulos y análisis de proporción.
- Exploración inicial con `.info()`, `.describe()`, `.head()`.

### Fase 2: Análisis Exploratorio (Celdas 8-22)
- Distribuciones univariadas (value_counts).
- Visualizaciones bivariadas (scatter plots, box plots, bar charts).
- Análisis de relaciones (edad vs gasto, ingresos vs gasto, frecuencia vs gasto).
- Identificación de clientes de alto valor (top 25%).

### Fase 3: Integración de Datos Externos (Celdas 23-27)
- Conexión a API de Yelp.
- Extracción de ratings promedio por ciudad.
- Merge con dataset principal.

### Fase 4: Análisis Final y Segmentación (Celdas 28-35)
- Visualizaciones con datos integrados.
- Clustering K-Means (4 clusters).
- Perfiles descriptivos de cada cluster.
- Recomendaciones por segmento.

---

## 📁 Estructura del Proyecto

```
proyecto/
├── README.md                           # Este archivo
├── RECOMMENDATIONS.md                  # Recomendaciones detalladas
├── Avance_1_EDA.ipynb                  # Notebook con análisis completo
└── base_datos_restaurantes_USA_v2.csv  # Dataset principal
```

---

## 🛠️ Requisitos Técnicos

### Dependencias
- **Python**: 3.11+
- **Librerías**:
  - `pandas` (manejo de datos)
  - `numpy` (operaciones numéricas)
  - `matplotlib` (visualización básica)
  - `seaborn` (visualización avanzada)
  - `scikit-learn` (clustering y normalización)
  - `requests` (API integration)

### Instalación
```bash
pip install pandas numpy matplotlib seaborn scikit-learn requests
```

---

## 🚀 Cómo Reproducir el Análisis

1. **Preparar el entorno**:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn requests
   ```

2. **Ejecutar el notebook**:
   ```bash
   jupyter notebook Avance_1_EDA.ipynb
   ```

3. **Ejecutar celdas en orden**:
   - Celda 1: Imports
   - Celda 2: Carga de datos
   - Celdas 3-7: Exploración y limpieza
   - Celdas 8-22: Análisis descriptivo
   - Celdas 23-27: Integración Yelp (requiere API key)
   - Celdas 28-35: Análisis final y recomendaciones

### Nota sobre API de Yelp
Para ejecutar las celdas de integración externa:
1. Obtener API key en https://www.yelp.com/developers
2. Reemplazar `API_KEY = 'TU_API_KEY_AQUI'` en la Celda 24
3. Ejecutar nuevamente

Sin API key válida, las celdas de extracción Yelp mostrarán errores (funcionalidad opcional).

---

## 📈 Visualizaciones Incluidas

1. **Distribuciones**: Personas por ciudad, estrato socioeconómico.
2. **Relaciones bivariadas**: Ingresos vs gasto, frecuencia vs gasto, edad vs consumo.
3. **Comparativas**: Gasto promedio por ciudad, ratings por ciudad.
4. **Segmentación**: Scatter PCA con clusters identificados.
5. **Distribuciones avanzadas**: Violin plots, box plots estratificados.

---

## 🎯 Uso de Hallazgos

Consulta **RECOMMENDATIONS.md** para:
- Recomendaciones estratégicas priorizadas
- Planes de acción concretos por área (Marketing, Operaciones, CRM)
- Segmentación aplicada para targeting
- KPIs para monitoreo
- Timeline de implementación

---

## 📞 Información Técnica

- **Rows**: 30,000 clientes
- **Columns**: 17 variables (ID, demográficas, comportamiento, preferencias, contacto)
- **Ciudades**: 10 principales en USA
- **Análisis de clustering**: K-Means con 4 clusters
- **Rango de datos**: Variables numéricas en escala diferente (edad: 18-80; ingresos: $2,000-$10,000; gasto: $20-$300)

---

## 📝 Notas

- El análisis utiliza técnicas de normalización para clustering (StandardScaler).
- Nulos no fueron imputados en EDA básico; requieren estrategia según columna para análisis predictivo.
- Contacto faltante (teléfono/correo) sugiere necesidad de campañas multi-canal.
- Correlaciones calculadas visualmente; para análisis estadístico formal, revisar correlación de Pearson/Spearman.

---

**Fecha de análisis**: Abril 2026  
**Versión**: 1.0
