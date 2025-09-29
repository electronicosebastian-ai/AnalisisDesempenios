# Analisis de Desempenos de Campa�as Trade Marketing 

# Análisis de Desempeño de Campañas de Trade Marketing

## Objetivo
Replicar un flujo de datos similar a Microsoft Fabric para evaluar campañas de Trade Marketing, desde la ingesta de datos hasta la visualización en Power BI.

## Estructura de Datos
- **Campañas**: id, nombre, fecha_inicio, fecha_fin, inversión, canal, región  
- **Ventas**: id, fecha, producto, unidades, valor, campaña_id  
- **Productos**: id, categoría, precio_lista, marca  
- **Puntos de venta**: id, ciudad, canal, segmento  

Relaciones:
- Campañas ↔ Ventas (1:N)  
- Ventas ↔ Productos (N:1)  
- Ventas ↔ Puntos de venta (N:1)  

## Arquitectura del Flujo
1. **Ingesta**: archivos brutos en `data/raw`  
2. **Transformación**: limpieza y estandarización en `data/staging` con PySpark  
3. **Data Lake**: almacenamiento en formato Parquet en `outputs/lake`  
4. **Warehouse**: carga de tablas limpias en PostgreSQL  
5. **Modelado**: cálculos de KPIs en notebooks (`notebooks/`)  
6. **Visualización**: dashboards en Power BI conectados al warehouse o Parquet  
7. **Documentación**: decisiones técnicas en `docs/`  