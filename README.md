# Reglas de Asociación con Apriori en Consumo Minorista

Este repositorio documenta un proyecto de aprendizaje no supervisado que emplea el algoritmo Apriori para analizar patrones de compra en transacciones de productos minoristas. A partir de una base simulada, se descubren reglas de asociación relevantes que permiten implementar recomendaciones de negocio.

## Objetivo

Aplicar minería de datos para identificar combinaciones frecuentes de productos y analizar sus relaciones a través de métricas como soporte, confianza y lift.

## Flujo de trabajo

### 1. Preparación de la base de datos
- Construcción del conjunto de datos `my_basket` con productos por ticket
- Expansión de los productos con `explode()`
- Transformación del dataset en una matriz binaria tipo cesta (`basket`)

### 2. Minería de reglas
- Aplicación del algoritmo Apriori con soporte mínimo de 25%
- Generación de reglas de asociación con filtros por:
  - Confianza (`min_threshold=0.5`)
  - Lift (`min_threshold=1.01`)
- Ordenamiento por fuerza de la asociación

### 3. Métricas analizadas
- Soporte, confianza, lift
- Leverage, conviction
- Métricas adicionales: Jaccard, Kulczynski, certeza, representatividad

### 4. Interpretación de patrones
- Identificación de pares como:
  - `(bread) → (butter)`
  - `(beer) → (chips)`
  - `(milk, beer) → (chips)`
- Reconocimiento de productos populares: `tomatoes`, `milk`, `onions`, `butter`
- Comparación de resultados entre confianza y lift para validar la solidez de las asociaciones

## Herramientas utilizadas

- Python 3.11  
- pandas  
- mlxtend  
- NumPy  
- matplotlib / seaborn (visualización opcional)

## Conclusiones

- Se identificaron combinaciones fuertemente relacionadas entre productos, útiles para promociones cruzadas y segmentación.
- El uso de múltiples métricas permitió una evaluación más precisa de las asociaciones.
- La metodología puede escalarse para datasets reales en entornos comerciales.
