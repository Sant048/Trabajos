# Clasificación de Variables

## Tipos de Variables Estadísticas

### Cualitativas Nominales (sin orden natural)

| Variable | Valores posibles | Notas |
|----------|-----------------|-------|
| **País Destino** | Estados Unidos, China, Singapur, Países Bajos, Reino Unido | 5 categorías |
| **Tipo de Producto** | 7 categorías (ver [[01_Ficha_Tecnica]]) | Sin jerarquía intrínseca |

### Cuantitativas Continuas (valores decimales posibles)

| Variable | Rango | Unidad |
|----------|-------|--------|
| **Valor Exportación** | $808 – $4,998,000 | USD |
| **Volumen** | 0.101 – 9.999 | Toneladas métricas |
| **Costo Logístico** | $806 – $20,681,430 | USD |
| **Arancel (%)** | 2.0% – 15.0% | Porcentaje |

### Cuantitativas Discretas (valores enteros)

| Variable | Rango | Notas |
|----------|-------|-------|
| **Tiempo de Entrega** | 2 – 45 días | Solo días completos |
| **Pedidos por País** | 1,608 – 3,346 | Conteo entero |

## Mnemónico de Clasificación

```
¿Se puede medir con número?
├── NO  → Cualitativa
│         ¿Tiene orden lógico? (pequeño/mediano/grande)
│         ├── SI → Cualitativa ORDINAL
│         └── NO → Cualitativa NOMINAL ← nuestro caso
└── SI  → Cuantitativa
          ¿Puede tomar valores decimales?
          ├── SI → Cuantitativa CONTINUA ← Valor, Volumen, Costo, Arancel
          └── NO → Cuantitativa DISCRETA ← Tiempo, Pedidos
```

---
← [[03_Limpieza_Calidad]] | → [[05_Frecuencias]]
