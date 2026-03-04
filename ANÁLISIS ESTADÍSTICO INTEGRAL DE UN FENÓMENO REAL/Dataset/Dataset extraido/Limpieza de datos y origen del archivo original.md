# Origen y Aislamiento de Datos
Al ser un dataset abiertamente grande compuesto por 20 hojas de excel, se aísla los datos de tal forma que el análisis **se enfoque en la variabilidad geográfica de las 32 ciudades principales y sus áreas metropolitanas. Para garantizar la solidez de la muestra y cumplir con el requerimiento de más de 1.000 observaciones, se consolidaron los registros históricos transformando los reportes mensuales por ciudad en una base de datos única. Este aislamiento permite comparar realidades económicas locales y asegura que el volumen de datos ($N$) sea suficiente para realizar inferencias estadísticas con un margen de error mínimo.**

## Ficha Técnica
- **Variable Independiente:** Ciudad (Cualitativa Nominal).
- **Variable Dependiente:** Tasa de Desocupación - TD (Cuantitativa Continua).
- **Variable de Apoyo:** Tasa de Ocupación - TO (Cuantitativa Continua).
- **Estructura:** Datos longitudinales (Panel) por ciudad y mes.
- **Tamaño de la Muestra ($N$):** 1,536 registros (32 ciudades × 48 meses).

##  Justificación del Cumplimiento
- **Volumen:** Al procesar 32 ciudades por un periodo amplio de meses, el dataset supera los 1,000 registros, cumpliendo estrictamente con la rúbrica de la asignatura.
- **Calidad:** Los datos provienen de la hoja "Año Móvil 32 Ciudades" de la GEIH, lo que garantiza que la información está verificada por el DANE bajo el marco censal 2018.

# Dataset 32 Ciudades N1536

## Metadata

|Campo|Detalle|
|---|---|
|**Archivo**|Dataset_32Ciudades_N1536.xlsx|
|**Hoja**|Dataset_32Ciudades_N1536|
|**Filas**|1,568|
|**Columnas**|17|
|**Filas duplicadas**|0|
|**Fuente**|DANE – Encuesta GEIH|
|**Cobertura geográfica**|32 ciudades principales de Colombia|
|**Tipo de serie**|Año móvil (ventanas deslizantes de 12 meses)|
|**Periodos únicos**|49|
|**Filas por ciudad**|49 (balanceado)|

## Descripción General

El dataset contiene **indicadores del mercado laboral colombiano** para las 32 ciudades principales del país, publicados por el DANE a través de la GEIH (Gran Encuesta Integrada de Hogares). Cada fila representa la combinación **ciudad × periodo de año móvil** — una ventana deslizante de 12 meses consecutivos (ej. "Ene - Dic 21", "Feb 21 - Ene 22"). El dataset está perfectamente balanceado: todas las ciudades tienen exactamente 49 observaciones.

## Diccionario de Variables

### Identificación

|Columna|Tipo|Nulos|Descripción|
|---|---|---|---|
|`Ciudad`|Texto|0|Nombre de la ciudad. 32 valores únicos|
|`Tipo de año`|Texto|0|Solo contiene `"Año móvil"` — **columna de un solo valor**|
|`periodo del tiempo`|Texto|0|Ventana de 12 meses, ej. `"Ene - Dic 21"`. 49 valores únicos|

**Las 32 ciudades:** Bogotá D.C., Medellín A.M., Cali A.M., Barranquilla A.M., Bucaramanga A.M., Manizales A.M., Pasto, Pereira A.M., Cúcuta A.M., Ibagué, Montería, Cartagena, Villavicencio, Tunja, Florencia, Popayán, Valledupar, Quibdó, Neiva, Riohacha, Santa Marta, Armenia, Sincelejo, Arauca, Yopal, Mocoa, Leticia, Inírida, San José del Guaviare, Mitú, Puerto Carreño, San Andrés

### Tasas del Mercado Laboral (%)

| Columna                              | Nulos | Media | Min   | Max   | Descripción                                        |
| ------------------------------------ | ----- | ----- | ----- | ----- | -------------------------------------------------- |
| `población en edad de trabajar`      | 0     | 77.4% | 68.5% | 84.1% | % de la población total en edad de trabajar        |
| `Tasa Global de Participación (TGP)` | 0     | 63.4% | 47.6% | 83.2% | Proporción de la PET activa en el mercado laboral  |
| `Tasa de Ocupación (TO)`             | 0     | 55.1% | 34.4% | 75.9% | Proporción de la PET que está ocupada              |
| `Tasa de Desocupación (TD)`          | 0     | 13.1% | 3.0%  | 31.4% | % de la fuerza laboral que está desempleada        |
| `Tasa de Subocupación (TS)`          | 0     | 7.1%  | 0.1%  | 16.4% | Proporción que trabaja menos horas de las deseadas |
| `Unnamed: 8`                         | 1,568 | —     | —     | —     | **Columna completamente vacía**                    |

### Población Absoluta (miles de personas)

| Columna                                   | Nulos | Media | Min | Max   | Descripción                              |
| ----------------------------------------- | ----- | ----- | --- | ----- | ---------------------------------------- |
| `Población total`                         | 0     | 802   | 11  | 8,068 | Población total de la ciudad             |
| `Población en edad de trabajar (PET)`     | 0     | 645   | 8   | 6,655 | Personas de 15+ años                     |
| `Fuerza de trabajo`                       | 0     | 421   | 4   | 4,698 | PET activa (ocupados + desocupados)      |
| `Población ocupada`                       | 0     | 374   | 4   | 4,311 | Personas con empleo                      |
| `Población desocupada`                    | 0     | 47    | 0   | 693   | Personas buscando empleo activamente     |
| `Población fuera de la fuerza de trabajo` | 0     | 224   | 3   | 2,141 | Inactivos                                |
| `Población subocupada`                    | 0     | 32    | 0   | 396   | Subempleados                             |
| `Fuerza de trabajo potencial`             | 0     | 22    | 0   | 293   | Disponibles pero no buscando activamente |

## Problemas Detectados

| #   | Problema                                                       | Columna afectada                                      | Severidad  |
| --- | -------------------------------------------------------------- | ----------------------------------------------------- | ---------- |
| 1   | Columna 100% vacía                                             | `Unnamed: 8`                                          | Alta       |
| 2   | Columna de un solo valor (redundante)                          | `Tipo de año`                                         | Media      |
| 3   | Nombre ambiguo: % vs absoluto                                  | `población en edad de trabajar`                       | Alta       |
| 4   | Espacios al final del nombre de columna                        | `población en edad de trabajar` , `Fuerza de trabajo` | Media      |
| 5   | Espaciado inconsistente en periodos                            | `periodo del tiempo`                                  | Media      |
| 6   | Sin variables de tiempo estructuradas                          | —                                                     | Media-Alta |
| 7   | Sin validación de consistencia entre tasas y valores absolutos | Tasas vs. poblaciones                                 | Media-Alta |
| 8   | Discrepancia entre N del nombre y filas reales                 | Nombre del archivo                                    |  Baja      |

## Estructura Lógica de las Variables

```
Población total
    └── Población en edad de trabajar (PET)
            ├── Fuerza de trabajo
            │       ├── Población ocupada
            │       │       └── Población subocupada
            │       └── Población desocupada
            ├── Población fuera de la fuerza de trabajo
            └── Fuerza de trabajo potencial
```

**Relaciones verificables:**

- `TGP = (Fuerza de trabajo / PET) × 100`
- `TO = (Población ocupada / PET) × 100`
- `TD = (Población desocupada / Fuerza de trabajo) × 100`
- `% PET = (PET / Población total) × 100`

