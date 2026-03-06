# Segmentación de Mercados por Cuantiles

## Estructura de Cuartiles

```
──────────────────────────────────────────────────────────────
      $0    $55,136    $176,700    $846,140    $1,842,050  $4,998,000
       |       Q1          Q2          Q3          P90          Max
       |←─ 25% ──→|←─ 25% ──→|←──── 25% ──────→|←── 10% ──→|
       
       Mercados      Mercados    Mercados        Mercados
       emergentes    estándar    relevantes      premium
──────────────────────────────────────────────────────────────
```

## Mercados Estratégicos (Valor > Q3 = $846,140)

| País Destino | Pedidos Estratégicos | Valor Promedio |
|-------------|---------------------|----------------|
| Países Bajos | 442 | $2,115,404 |
| China | 384 | $2,076,538 |
| Estados Unidos | 849 | $2,067,809 |
| Reino Unido | 432 | $2,041,586 |
| Singapur | 393 | $1,995,217 |

> [!success] Hallazgo
> Todos los países destino tienen representación en el segmento estratégico, con valores promedio entre $1.99M y $2.12M. Países Bajos lidera en valor promedio, mientras que Estados Unidos concentra el mayor número de pedidos estratégicos (849).

## Rango Intercuartílico (IQR)

```
IQR = Q3 - Q1 = $846,140 - $55,136 = $791,004
```

El IQR representa el **rango del 50% central** de las operaciones. Es una medida robusta que no se ve afectada por valores extremos.

## Recomendaciones de Segmentación

| Segmento | Umbral | Estrategia |
|----------|--------|-----------|
| **Premium** | > P90 ($1.84M) | SLA garantizado, ejecutivo de cuenta dedicado |
| **Estratégico** | > Q3 ($846K) | Monitoreo prioritario, rutas optimizadas |
| **Estándar** | Q1-Q3 | Operación regular con seguimiento estándar |
| **Emergente** | < Q1 ($55K) | Evaluar viabilidad logística por costo unitario |

---
← [[07_Medidas_Descriptivas]] | → [[09_Outliers_Boxplot]]
