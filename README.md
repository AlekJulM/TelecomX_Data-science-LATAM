# Telecom X - Churn Analysis 📈

## Descripción

Este repositorio contiene el análisis de evasión de clientes (Churn) para Telecom X, realizado por Alexander Jamin Julon Mayta. El objetivo del proyecto es identificar los principales factores que influyen en la decisión de los clientes de abandonar el servicio y proponer recomendaciones estratégicas para reducir la tasa de churn.

## Tabla de Contenidos

* [Requisitos](#requisitos)
* [Instalación](#instalación)
* [Estructura del Proyecto](#estructura-del-proyecto)
* [Fuente de Datos](#fuente-de-datos)
* [Preprocesamiento y Transformación](#preprocesamiento-y-transformación)
* [Análisis Exploratorio de Datos](#análisis-exploratorio-de-datos)
* [Resultados Clave](#resultados-clave)
* [Recomendaciones](#recomendaciones)
* [Uso](#uso)
* [Autor](#autor)
* [Licencia](#licencia)

## Requisitos

* Python 3.8 o superior
* Bibliotecas:

  * pandas
  * numpy
  * matplotlib
  * seaborn

## Instalación

```bash
# Clonar el repositorio
git clone https://github.com/AlekJulM/TelecomX_Data-science-LATAM.git
cd TelecomX_Data-science-LATAM

# Crear entorno virtual (opcional)
python -m venv venv
source venv/bin/activate  # Linux/MacOS
venv\Scripts\activate   # Windows

# Instalar dependencias
pip install -r requirements.txt
```

## Estructura del Proyecto

```
TelecomX_Data-science-LATAM/

├── TelecomX_Data.json # Datos brutos en formato JSON
│  TelecomX_LATAM.ipynb #creado en Collab
├── TelecomX_diccionario.md   #Archivo con las columnas y su información del dataset
└── README.md    # Documentación del proyecto
```

## Fuente de Datos

* Datos obtenidos del archivo `TelecomX_Data.json` alojado en el repositorio original de Telecom X.
* Contiene información de clientes: demografía, tipo de contrato, consumo y estado de churn.

## Preprocesamiento y Transformación

1. **Normalización de datos**: Uso de `pd.json_normalize()` para convertir estructuras JSON anidadas en columnas planas.
2. **Ajuste de tipos y corrección de valores**:

   * Transformación de columnas binarias (`Partner`, `Dependents`, `PhoneService`) a tipo numérico.
   * Reemplazo de valores faltantes en `Charges.Total` por 0 y conversión a `float`.
3. **Gestión de valores faltantes**:

   * Eliminación de registros con churn faltante (< 3% del total).
4. **Ingeniería de características**:

   * Creación de la columna `Cuentas_Diarias` (tarifa diaria promedio del cliente).

## Análisis Exploratorio de Datos

Se generaron visualizaciones para:

* **Estado de Clientes**: Proporción de clientes activos vs. inactivos.
* **Método de Pago de Clientes Inactivos**: Distribución de métodos de pago entre churners.
* **Distribución por Género**: Comparación de churn por género.
* **Distribución por Contrato**: Tasa de churn según tipo de contrato.
* **Total Gastado vs. Churn**: Boxplot del gasto total de activos vs. inactivos.
* **Churn por Edad**: Tasa de churn en menores vs. mayores de 65 años.

## Resultados Clave

* Los contratos mes a mes presentan una tasa de churn significativamente mayor.
* El uso de cheque electrónico como método de pago está correlacionado con mayor churn.
* Los clientes mayores de 65 años tienen una probabilidad más alta de abandonar.
* Los churners tienden a haber gastado menos en total.

## Recomendaciones

* **Incentivar contratos a largo plazo**: Ofrecer descuentos/promociones para planes de uno y dos años.
* **Revisar método de pago**: Investigar por qué usuarios de cheque electrónico tienen mayor propensión a churn.
* **Segmentación por edad**: Diseñar programas de fidelización para clientes seniors (>65 años).
* **Monitoreo de gasto**: Detectar clientes de bajo gasto y ofrecerles paquetes personalizados.

## Uso

```bash
# Ejecutar el notebook de análisis
jupyter notebook notebooks/churn_analysis.ipynb

# Ejecutar scripts de ETL
python scripts/extract.py
python scripts/transform.py
python scripts/clean.py
```

## Autor

**Alexander Jamin Julon Mayta**

## Licencia

Distribuido bajo la licencia MIT. Véase `LICENSE` para más detalles.
