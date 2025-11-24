# Wine Clustering Lab: Comparativa de Algoritmos No Supervisados

## Descripción General
Este laboratorio de Ciencia de Datos analizamos el dataset **Wine** de *sklearn* para descubrir patrones ocultos y comparar el desempeño de cuatro enfoques de clustering:

- **Partición** (K-Means)  
- **Probabilidad** (Gaussian Mixture Models)  
- **Jerárquico** (Ward)  
- **Densidad** (DBSCAN)

El proyecto incluye un pipeline completo con preprocesamiento, PCA, modelado comparativo y evaluación rigurosa mediante métricas técnicas como **Silhouette, ARI, DBI y NMI**.

---

##  Pipeline del Proyecto

1. **EDA y Preprocesamiento**
   - Limpieza general del dataset.
   - Estandarización con `StandardScaler` para evitar sesgos por escala.
   - **Semillas aleatorias (`random_state`) fijadas** para asegurar resultados replicables.

2. **Reducción de Dimensionalidad**
   - Aplicación de **PCA** para visualizar separación de clases en 2D.
   - Análisis de patrones y separabilidad antes del clustering.

3. **Modelado Comparativo**
   - **K-Means:** Optimizado con método del codo y Silhouette (`k=3`).
   - **GMM:** Ajustado con covarianza *full*.
   - **Jerárquico (Ward):** Minimización de varianza entre clusters.
   - **DBSCAN:** Pruebas con múltiples valores de `eps` para evaluar densidad.

4. **Evaluación de Métricas**
   - Métricas ciegas: **Silhouette, DBI**
   - Métricas supervisadas: **ARI, NMI**
   - Comparación contra el *ground truth* del dataset.

---

## Resultados Clave

### Los Ganadores: K-Means & GMM
- **ARI:** 0.8975  
- **Silhouette:** 0.28  
- Los datos presentan **estructura convexa y globular**, ideal para métodos basados en centroides.  
- K-Means y GMM entregan prácticamente el mismo rendimiento.

###  El Caso Fallido: DBSCAN
- ARI: **0.22**
- Silhouette: **negativo**
- La densidad del dataset es demasiado variable; DBSCAN clasificó buena parte de los datos como ruido.

### Conclusión Técnica
Para este dataset, **K-Means (`k=3`)** es la solución óptima:  
Eficiente, interpretable y con el mejor balance entre precisión y costo computacional.

---

##  Stack Tecnológico

- **Lenguaje:** Python  3.12.7
- **Librerías:**  
  - Scikit-learn  
  - Pandas  
  - NumPy  
  - Matplotlib  
  - Seaborn  
- **Entorno:** Jupyter Notebook / Anaconda  

