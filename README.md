# Análisis de clientes de tarjeta de crédito (UCI Credit Card)

## Origen de los datos
- Dataset: "Default of Credit Card Clients", del repositorio UCI Machine Learning.
- Contenido: 30.000 clientes y 25 columnas (límite de crédito, sexo, educación,
  estado civil, edad, historial de pagos, montos facturados y pagados, y si
  cayó en default el mes siguiente).
- Archivo usado: UCI_Credit_Card.csv

## Decisiones de limpieza
| Problema detectado | Qué se hizo | Por qué |
|---|---|---|
| Valores faltantes (NaN) | No se encontraron (0 nulos) | Se verificó con isna().sum() |
| Duplicados | No se encontraron (0 filas ni ID repetidos) | Se verificó con duplicated() |
| EDUCATION con códigos 0, 5 y 6 (345 casos) | Se convirtieron a NaN y se imputaron con la moda | No figuran en la documentación |
| MARRIAGE con código 0 (54 casos) | Se convirtió a NaN y se imputó con la moda | No figura en la documentación |
| Tipos de datos | SEX, EDUCATION, MARRIAGE y default pasaron a category | Son categorías, no cantidades |
| Fechas | No aplica | El dataset no tiene columnas de fecha |
| BILL_AMT negativos | No se modificaron | Representan saldo a favor, es un valor válido |

## Agrupaciones realizadas
- Default por nivel educativo
- Límite de crédito promedio por sexo
- Default según el rango de límite de crédito
- Edad promedio por sexo

## Cómo reproducir
1. Descargar UCI_Credit_Card.csv (incluido en este repositorio).
2. Abrir y ejecutar de principio a fin el notebook Limpieza_datos_pandas.ipynb.
