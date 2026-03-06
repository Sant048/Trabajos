
# 📦 Boxplot y Valores Atípicos

## Estructura del Boxplot

```
               ┌─────────┬──────────────────────┐
               │         │                      │
  ──── whisker ┤   Q1    │  Q2         Q3       ├── whisker ──── outliers ●●●
               │ $55,136 │ $176,700  $846,140   │
               └─────────┴──────────────────────┘
               
Min válido: ~$0 (ningún valor inferior)
Max válido: $2,032,646
Outliers superiores: > $2,032,646
```

## Cálculo de Límites (Regla 1.5×IQR)

```python
IQR = 791,004
Límite inferior = Q1 - 1.5×IQR = 55,136 - 1,186,506 = -$1,131,370
  → No hay outliers inferiores (todos los valores son positivos)

Límite superior = Q3 + 1.5×IQR = 846,140 + 1,186,506 = $2,032,646
  → 859 pedidos superan este umbral (8.6% del total)
```

## Outliers detectados

### Estadísticas de Outliers
- **Total:** 859 registros (8.6% del dataset)
- **Tipo:** 100% outliers superiores (valores muy altos)
- **Valor mínimo outlier:** > $2,032,647
- **Valor máximo:** $4,998,000

### Composición por Producto
Los outliers corresponden principalmente a:
1. **Semiconductors** – $500/kg × pedidos grandes (~5-10 ton) = $2.5M–$5M
2. **Pharmaceuticals** – $200/kg × pedidos grandes = $1M–$2M

### Impacto Comercial de Mercados Extremos

> [!important] Decisión estratégica
> Los outliers **NO deben eliminarse**. Representan los contratos más valiosos de la empresa:
> - Semiconductors para destinos tech (Singapur, China)
> - Pharma para destinos Europa (Países Bajos, Reino Unido)
> 
> Estos pedidos extremos son precisamente los **mercados más rentables** a proteger.

---
← [[08_Cuantiles_Segmentacion]] | → [[10_Analisis_Estrategico]]
