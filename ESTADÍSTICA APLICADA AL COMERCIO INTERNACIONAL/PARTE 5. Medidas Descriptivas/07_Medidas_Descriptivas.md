# Medidas Descriptivas – Valor de Exportación (USD)

## Tendencia Central

| Medida | Valor | Interpretación |
|--------|-------|----------------|
| **Media** | $662,999 | Valor promedio elevado; influenciado por exportaciones de alto valor |
| **Mediana** | $176,700 | La mitad de los pedidos están por debajo de este valor |
| **Moda** | $22,920 | El valor más repetido corresponde a pedidos pequeños de materias primas |

> [!important] Media vs Mediana
> La media ($662,999) es **3.75× mayor** que la mediana ($176,700). Esto confirma que la distribución está **sesgada por valores extremos** (Semiconductores, Farmacéuticos).

## Dispersión

| Medida | Valor | Interpretación |
|--------|-------|----------------|
| **Varianza** | $1.04 × 10¹² | Altísima dispersión total |
| **Desviación Estándar** | $1,017,449 | En promedio, los pedidos se desvían ±$1M de la media |
| **Coef. de Variación (CV)** | **153.5%** | Distribución MUY heterogénea e inestable |

### CV
El coeficiente de variación **indica el grado de estabilidad** del comercio:
- CV < 33% → Comercio estable y homogéneo
- CV 33-67% → Moderadamente heterogéneo
- CV > 100% → **Muy heterogéneo e inestable** ← nuestro caso (153.5%)
## Forma de la Distribución

| Medida | Valor | Interpretación |
|--------|-------|----------------|
| **Asimetría (Skewness)** | +2.30 | Asimetría positiva → cola hacia la derecha |
| **Curtosis (Kurtosis)** | +5.07 | Leptocúrtica → pico pronunciado, colas pesadas |

```
Distribución Normal: Asimetría=0, Curtosis=3
Nuestra distribución: Asimetría=+2.30, Curtosis=+5.07
→ Pico muy alto (muchos pedidos pequeños) + cola derecha larga (pocos pedidos enormes)
```
## Cuantiles

| Cuantil | Valor (USD) | Significado |
|---------|------------|-------------|
| Q1 – 25% | $55,136 | 25% de pedidos menores a este valor |
| Q2 – Mediana | $176,700 | Valor central |
| Q3 – 75% | $846,140 | 75% de pedidos menores a este valor |
| **Percentil 90** | **$1,842,050** | Solo el 10% supera este umbral |
| **IQR** | **$791,004** | Rango del 50% central de los datos |

---
← [[06_Pareto]] | → [[08_Cuantiles_Segmentacion]]
