# **Análisis Predictivo de Riesgo Crediticio con Machine Learning: Un Enfoque Comparativo entre Scikit-learn y PySpark**

## **Contexto del Proyecto**

En la industria financiera moderna, la evaluación precisa del riesgo crediticio representa uno de los desafíos más críticos para instituciones prestamistas. La capacidad de predecir la probabilidad de incumplimiento de un préstamo no solo impacta directamente en la rentabilidad, sino también en la estabilidad del sistema financiero. Este proyecto aborda este desafío mediante la implementación y comparación de modelos de machine learning para la predicción de impagos, utilizando una de las bases de datos de préstamos más comprehensivas disponibles públicamente.

## **Base de Datos: Lending Club Dataset**

### **Origen y Relevancia**
El dataset de Lending Club constituye un benchmark estándar en la industria fintech, conteniendo información histórica de más de **2.2 millones de préstamos** originados entre 2007 y 2020. Lending Club, como plataforma de préstamos peer-to-peer líder, proporciona este dataset que se ha convertido en un recurso fundamental para la investigación en riesgo crediticio.

### **Características Principales**
- **Volumen:** 2,260,701 registros de préstamos.
- **Variables:** 151 características iniciales por préstamo.
- **Período:** Datos históricos acumulados por más de una década.
- **Completitud:** Información crediticia verificada y estructurada.

## **Variables Clave Analizadas**

### **Variables Demográficas y de Solicitud**
- `loan_amnt`: Monto del préstamo solicitado.
- `term`: Plazo del préstamo (36/60 meses)
- `int_rate`: Tasa de interés asignada.
- `grade`: Grado crediticio asignado (A-G).
- `purpose`: Propósito del préstamo.

### **Variables de Historial Crediticio**
- `fico_range_low/high`: Rango de score FICO del solicitante.
- `annual_inc`: Ingreso anual del solicitante.
- `dti`: Ratio deuda-ingreso.
- `revol_util`: Porcentaje de utilización de crédito revolving.
- `inq_last_6mths`: Consultas crediticias recientes.

### **Variables de Resultado**
- `loan_status`: Estado final del préstamo
- `default`: Variable objetivo binaria (1=impago, 0=pago exitoso).

## **Objetivos del Análisis**

### **Primario**
Desarrollar un modelo predictivo capaz de identificar préstamos con alta probabilidad de default utilizando técnicas de machine learning, optimizando el trade-off entre detección temprana de riesgo y minimización de falsas alarmas.

### **Secundarios**
- Comparar el rendimiento de implementaciones en Scikit-learn vs PySpark.
- Identificar las variables más predictivas del riesgo crediticio.
- Evaluar estrategias para manejar el desbalance inherente en datos crediticios.