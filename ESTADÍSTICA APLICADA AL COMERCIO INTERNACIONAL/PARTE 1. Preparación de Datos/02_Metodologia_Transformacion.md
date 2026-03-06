# Metodología de Transformación y Creación de Columnas

## Objetivo
Construir las **8 variables obligatorias** del taller a partir de los datos logísticos originales, aplicando fórmulas técnicas reproducibles en Excel/Python.
## Las 8 Columnas Derivadas

### 1.  País Destino
```
Origen: Destination_City
Fórmula: EXTRAE el código de país después de la coma
Ejemplo: "Los Angeles, US" → "Estados Unidos"
Tipo: Cualitativa Nominal
```

### 2.  Valor de Exportación (USD)
```
Origen: Order_Weight_Kg × Valor_Unitario_por_Categoría
Tabla de valores unitarios:
  - Semiconductors:        $500/kg
  - Pharmaceuticals:       $200/kg
  - Consumer Electronics:  $120/kg
  - Auto Parts:             $60/kg
  - Textiles:               $15/kg
  - Perishable Foods:       $10/kg
  - Raw Materials:           $8/kg
Excel: =Order_Weight_Kg * BUSCARV(Product_Category, tabla_valores, 2, 0)
Tipo: Cuantitativa Continua
```
### 3. Volumen Exportado (Toneladas)
```
Origen: Order_Weight_Kg
Fórmula: =Order_Weight_Kg / 1000
Tipo: Cuantitativa Continua
```

### 4.  Tiempo de Entrega (Días)
```
Origen: Actual_Lead_Time_Days (uso directo)
Sin transformación
Tipo: Cuantitativa Discreta
```

### 5.  Costo Logístico (USD)
```
Origen: Shipping_Cost_USD (uso directo)
Incluye flete + seguro por pedido
Tipo: Cuantitativa Continua
```
### 6.  Tipo de Producto
```
Origen: Product_Category (uso directo)
Sin transformación
Tipo: Cualitativa Nominal
```
### 7. Arancel (%)
```
Lógica: Base por categoría + modificador por ruta
Bases:
  Textiles: 12% | Pharmaceuticals: 2% | Semiconductors: 5%
  Consumer Electronics: 8% | Raw Materials: 3%
  Auto Parts: 10% | Perishable Foods: 15%
Modificadores de ruta:
  Pacific: +1% | Suez: +2% | Atlantic: +1.5%
  Intra-Asia: +0% | Commodity: +0.5%
Máximo: 15%
Excel: =MIN(BUSCARV(Product_Category,base,2,0) + BUSCARV(Route_Type,mod,2,0), 15)
Tipo: Cuantitativa Continua
```
### 8. Pedidos por País
```
Origen: Conteo agrupado por País_Destino
Excel: =COUNTIF(Pais_Destino_col, pais_actual)
Tipo: Cuantitativa Discreta
```
## Diagrama de Flujo de Transformación

```
Dataset Original (19 columnas, 10,000 registros)
          ↓
    [Limpieza]
          ↓
    [Extracción País]  →  Pais_Destino
    [Cálculo Valor]    →  Valor_Exportacion_USD
    [División Peso]    →  Volumen_Toneladas
    [Tiempo Directo]   →  Tiempo_Entrega_Dias
    [Costo Directo]    →  Costo_Logistico_USD
    [Categoría]        →  Tipo_Producto
    [BUSCARV Arancel]  →  Arancel_Pct
    [COUNTIF País]     →  Pedidos_Por_Pais
          ↓
  Dataset Transformado (15 columnas, 10,000 registros)
```

---
← [[01_Ficha_Tecnica]] | → [[03_Limpieza_Calidad]]
