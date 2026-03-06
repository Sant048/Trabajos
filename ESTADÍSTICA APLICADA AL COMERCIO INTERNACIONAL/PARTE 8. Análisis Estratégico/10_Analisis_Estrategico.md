# Análisis Estratégico y Conclusiones

## 8.1 ¿El comercio está concentrado o diversificado?

**Respuesta: Moderadamente concentrado con alta heterogeneidad interna**

- Solo **6 países destino** y **7 categorías de producto**
- Estados Unidos concentra el **33.5%** de los pedidos → riesgo de dependencia
- CV = 153.5% → los volúmenes individuales son extremadamente variables
- **Recomendación:** Diversificar incorporando mercados de Sudeste Asiático y África subsahariana

## 8.2 País con mayor dependencia comercial

🇺🇸 **Estados Unidos**
- 3,346 pedidos (33.5% del total)
- $2,256,551,948 en valor exportado (34% del total)
- Rutas: Pacific + Atlantic
- **Riesgo:** Alta exposición a cambios arancelarios y políticas comerciales de EE.UU.

## 8.3 Variabilidad logística internacional

| Ruta | Características |
|------|----------------|
| **Intra-Asia** | Tiempos cortos, menor variabilidad |
| **Pacific** | Alta frecuencia, moderada variabilidad |
| **Atlantic** | Mayor exposición climática |
| **Suez** | Alta sensibilidad geopolítica, aranceles +2% |

- Tiempo promedio: ~15.4 días | Desviación: ~8.2 días
- Retrasos extremos correlacionados con `Disruption_Event`

## 8.4 Principal factor de retrasos

 **Problemas aduaneros (30.4%)** — Ver análisis completo en [[06_Pareto]]

Causa raíz: **administrativa/operacional**, no geopolítica ni climática → 100% controlable con inversión en digitalización.

## 8.5 Recomendaciones Estratégicas Finales

###  Alta prioridad (impacto × viabilidad)

1. **Digitalización aduanera**
   - Impacto: Reduce 30.4% de los retrasos
   - Inversión: Media
   - Plazo: 3-6 meses

2. **Gestión documental proactiva**
   - Checklist digital obligatorio antes de despacho
   - Reduce causas 1+3 (47.8% de retrasos combinados)

### Media prioridad

3. **Optimización de rutas por producto**
   - Semiconductores → Pacific/Intra-Asia (menor tiempo)
   - Perecederos → Intra-Asia exclusivo
   - Textiles → evaluar Atlantic vs Suez por aranceles

4. **Diversificación de mercados**
   - Meta: Ningún mercado > 25% del total
   - Incorporar Vietnam, India, Brasil, Marruecos

### Largo plazo

5. **Sistema predictivo de riesgos**
   - Integrar `Geopolitical_Risk_Index` y `Weather_Severity_Index` del dataset
   - Alertas tempranas para rutas Suez y Atlantic

## Resumen Ejecutivo

> El análisis de 10,000 operaciones reales del período 2024-2025 revela que la empresa tiene un comercio **técnicamente sólido** pero **estratégicamente vulnerable** por la dependencia en Estados Unidos (33.5%) y los problemas administrativos evitables que causan el 71.7% de los retrasos. Las exportaciones de alto valor (Semiconductores, Farmacéuticos) generan valor desproporcionado y deben tener protección logística prioritaria.

---
← [[09_Outliers_Boxplot]] | ↩ [[00_INDEX]]
