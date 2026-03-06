
#  Protocolo de Limpieza y Calidad de Datos

## Controles Aplicados

### 1. Validación de Integridad
- **Criterio:** Eliminación de registros con `Order_Weight_Kg` ≤ 0
- **Resultado:** 0 registros eliminados (dataset limpio desde origen)
- **Registros finales:** 10,000

### 2. Tratamiento de Valores Faltantes

| Columna | Valores Faltantes | Tratamiento |
|---------|------------------|-------------|
| `Disruption_Event` | 8,733 (87.3%) | Se conservan → representan operaciones **sin evento de disrupción** |
| Resto de columnas | 0 | Sin tratamiento necesario |

> [!info] Decisión metodológica
> Los `NaN` en `Disruption_Event` **NO son errores** de captura. Su ausencia es información válida: el pedido llegó sin ningún evento disruptivo.

### 3. Tratamiento de Anomalías (Delay_Days)

- Los retrasos extremos en `Delay_Days` se **conservan en la muestra**
- Son hechos reales derivados de `Disruption_Event` (conflictos geopolíticos, clima severo)
- Son útiles para el análisis de riesgo logístico

### 4. Estandarización

```
Fechas:  → formato YYYY-MM-DD
Moneda:  → USD (dólares americanos)
País:    → nombres completos en español
Peso:    → kilogramos (origen) y toneladas (derivada)
```

### 5. Detección de Outliers

**Método:** Regla 1.5 × IQR (Tukey)

```
IQR = Q3 - Q1 = $846,140 - $55,136 = $791,004
Límite inferior = Q1 - 1.5×IQR = 55,136 - 1,186,506 = < 0 (ninguno inferior)
Límite superior = Q3 + 1.5×IQR = 846,140 + 1,186,506 = $2,032,646
```

- **Outliers detectados:** 859 registros (8.6%)
- **Naturaleza:** Exportaciones legítimas de Semiconductores ($500/kg) y Farmacéuticos ($200/kg)
- **Decisión:** Se conservan → representan mercados de alto valor real

---
← [[02_Metodologia_Transformacion]] | → [[04_Clasificacion_Variables]]
