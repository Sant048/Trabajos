# Ficha Técnica del Dataset

## Origen y Características

| Campo | Detalle |
|-------|---------|
| **Nombre** | Global Supply Chain Disruption & Resilience Dataset |
| **Volumen** | 10,000 registros |
| **Período** | 2024 – 2025 |
| **Contexto** | Análisis de competitividad global frente a disrupciones logísticas |

## Rutas Comerciales

| Ruta | Descripción |
|------|-------------|
| **Pacific** | Asia → América del Norte/Sur |
| **Suez** | Asia → Europa/Mediterráneo |
| **Atlantic** | América → Europa |
| **Intra-Asia** | Movimientos dentro del continente asiático |
| **Commodity** | Rutas de materias primas |

## Países Destino (6 mercados)

| País | Código | Mercado |
|------|--------|---------|
| Estados Unidos | US | Los Angeles, New York |
| China | CN | Shanghai |
| Singapur | SG | Singapore |
| Países Bajos | NL | Rotterdam |
| Reino Unido | UK | Felixstowe |

## Categorías de Producto (7 tipos)

| Producto | Valor Unitario (USD/kg) | Clasificación |
|----------|------------------------|---------------|
| Semiconductors | $500 | Alto valor |
| Pharmaceuticals | $200 | Alto valor |
| Consumer Electronics | $120 | Valor medio-alto |
| Auto Parts | $60 | Valor medio |
| Textiles | $15 | Valor bajo-medio |
| Perishable Foods | $10 | Valor bajo |
| Raw Materials | $8 | Valor bajo |

## Variables Originales del Dataset

```
Order_ID, Order_Date, Origin_City, Destination_City,
Route_Type, Transportation_Mode, Product_Category,
Base_Lead_Time_Days, Scheduled_Lead_Time_Days, Actual_Lead_Time_Days,
Delay_Days, Delivery_Status, Disruption_Event,
Geopolitical_Risk_Index, Weather_Severity_Index, Inflation_Rate_Pct,
Shipping_Cost_USD, Order_Weight_Kg, Mitigation_Action_Taken
```

## Notas de Calidad

> [!warning] Valores Faltantes
> `Disruption_Event` tiene 8,733 valores nulos → representan operaciones **sin disrupción** (normal).

> [!check] Integridad
> 0 registros con `Order_Weight_Kg` nulo o negativo eliminados.

---
← [[00_INDEX]] | → [[02_Metodologia_Transformacion]]
