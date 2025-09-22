# **Conclusiones del Proyecto: Análisis Comparativo**

## **Rendimiento Computacional: ¿Qué entorno fue más rápido?**

**PySpark demostró superioridad en escalabilidad:**
- **Reducción del 15% en tiempo de entrenamiento** (34 vs 40 minutos) para el mismo grid search.
- **Ventaja más significativa en datasets grandes** (>1GB) donde el procesamiento distribuido muestra su verdadero valor.
- **Scikit-learn fue más eficiente en subsets pequeños** debido a la sobrecarga de inicialización de Spark.

**Veredicto:** PySpark es más rápido para volúmenes de datos donde el procesamiento distribuido puede paralelizar efectivamente las operaciones.

## **Precisión Predictiva: ¿Cuál fue más preciso?**

**PySpark obtuvo un rendimiento ligeramente superior:**

| Métrica | Scikit-learn | PySpark | Mejora |
|---------|--------------|---------|---------|
| **AUC-ROC** | 0.6985 | 0.7160 | +2.5% |
| **Accuracy** | 0.6217 | 0.6490 | +4.4% |
| **F1-Score** | 0.2959 | 0.3112 | +5.2% |

**Factores clave de la mejora:**
- Mejor manejo nativo del desbalance de clases en PySpark.
- Implementación más optimizada del Random Forest distribuido.
- Procesamiento más estable de variables categóricas.

## **Aplicabilidad: ¿Cuándo es útil PySpark?**

**Usar PySpark cuando:**
- **Volúmenes de datos > 10GB** que exceden la memoria RAM disponible.
- **Procesos ETL complejos** que requieren transformaciones distribuidas.
- **Entornos productivos** con infraestructura clusterizada.
- **Flujos de trabajo** que integran múltiples fuentes de big data.

**Use Scikit-learn cuando:**
- ✅ **Datasets caben en memoria** (<10GB).
- ✅ **Prototipado rápido** y experimentación iterativa.
- ✅ **Algoritmos especializados** no disponibles en MLlib.
- ✅ **Recursos computacionales limitados** (equipos de desarrollo).

## **Interpretabilidad: ¿Qué aporta LIME?**

**LIME demostró ser invaluable para:**

### **Transparencia del Modelo**
- **Explicaciones locales** para predicciones individuales.
- **Identificación de razones** detrás de errores específicos.
- **Validación de lógica de negocio** en decisiones del modelo.

### **Debugging y Mejora**
- **Detección de sesgos** en variables categóricas (ej: sobrepeso en `verification_status`).
- **Identificación de features problemáticas** que causan falsos positivos.
- **Optimización de thresholds** basada en contribuciones reales de variables.

##  **Conclusión General**

**PySpark representa la opción más robusta para implementaciones productivas** a escala, mientras que **Scikit-learn mantiene ventajas en desarrollo y prototipado**. La **ligera superioridad predictiva de PySpark** (AUC 0.716 vs 0.699) justifica su complejidad operativa en entornos adecuados.

**La combinación ideal** sería utilizar Scikit-learn para desarrollo inicial y PySpark para implementación final, con LIME como herramienta permanente de interpretabilidad y validación del modelo.
