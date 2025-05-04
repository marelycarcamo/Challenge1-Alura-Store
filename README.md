# 📊 Alura Store Latam – Análisis Comparativo de Tiendas

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![Pandas](https://img.shields.io/badge/Pandas-2.2.2-150458.svg)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10.0-11557c.svg)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.13.2-77AB43.svg)](https://seaborn.pydata.org/)

Este repositorio contiene un análisis de datos completo sobre la cadena **Alura Store**, evaluando el rendimiento de sus cuatro tiendas para determinar si alguna debería cerrarse antes de iniciar un nuevo emprendimiento.

![Banner del proyecto](https://raw.githubusercontent.com/username/AluraStoreLatam/main/images/banner.png)

## 📌 Índice

1. [📋 Resumen Ejecutivo](#-resumen-ejecutivo)
2. [🎯 Objetivos del Proyecto](#-objetivos-del-proyecto)
3. [💾 Conjunto de Datos](#-conjunto-de-datos)
4. [🔧 Requisitos e Instalación](#-requisitos-e-instalación)
5. [📁 Estructura del Repositorio](#-estructura-del-repositorio)
6. [🧹 Proceso de Limpieza de Datos](#-proceso-de-limpieza-de-datos)
7. [📊 Análisis y Visualizaciones](#-análisis-y-visualizaciones)
8. [🔍 Hallazgos Clave](#-hallazgos-clave)
9. [📝 Conclusiones y Recomendaciones](#-conclusiones-y-recomendaciones)
10. [🤝 Cómo Contribuir](#-cómo-contribuir)
11. [📚 Referencias y Recursos](#-referencias-y-recursos)
12. [👤 Autora](#-autora)

## 📋 Resumen Ejecutivo

El Sr. Juan, propietario de Alura Store, está evaluando cerrar una de sus cuatro tiendas para invertir en un nuevo emprendimiento. Este proyecto analiza datos de ventas, rendimiento y satisfacción del cliente para determinar si esta decisión sería acertada y, de serlo, cuál tienda debería cerrarse.

**Resultado principal:** Tras un análisis exhaustivo, se determinó que todas las tiendas presentan un rendimiento equilibrado y saludable, por lo que no se recomienda cerrar ninguna.

## 🎯 Objetivos del Proyecto

- Analizar el rendimiento financiero de cada tienda
- Evaluar patrones de venta por categoría de producto
- Medir la satisfacción del cliente a través de calificaciones
- Identificar productos más y menos vendidos
- Comparar costos logísticos (envío) entre tiendas
- Proporcionar una recomendación basada en datos

## 💾 Conjunto de Datos

El análisis se basa en datos de ventas de las cuatro tiendas de Alura Store. Los datos incluyen:

| Variable | Descripción |
|----------|-------------|
| Producto | Nombre del producto vendido |
| Categoría del Producto | Clasificación del producto |
| Precio | Valor de venta en moneda local |
| Costo de envío | Costo logístico asociado |
| Fecha de Compra | Día de la transacción |
| Vendedor | Nombre del vendedor |
| Lugar de Compra | Ciudad donde se realizó la venta |
| Calificación | Valoración del cliente (1-5 estrellas) |
| Método de pago | Forma de pago utilizada |
| Cantidad de cuotas | Número de plazos para el pago |
| Latitud | Coordenada geográfica |
| Longitud | Coordenada geográfica |

Total de registros: 9,435 transacciones

## 🔧 Requisitos e Instalación

### Prerrequisitos
- Python 3.11 o superior
- Gestor de paquetes pip

### Pasos de instalación

1. **Clonar este repositorio**
   ```bash
   git clone https://github.com/username/AluraStoreLatam.git
   cd AluraStoreLatam
   ```

2. **Crear un entorno virtual**
   ```bash
   python -m venv venv
   source venv/bin/activate    # En macOS/Linux
   venv\Scripts\activate       # En Windows
   ```

3. **Instalar dependencias**
   ```bash
   pip install -r requirements.txt
   ```

### Dependencias principales

```
pandas==2.2.2
seaborn==0.13.2
matplotlib==3.10.0
unidecode==1.3.8
```

## 📁 Estructura del Repositorio

```
AluraStoreLatam/
├── notebooks/
│   └── AluraStoreLatam.ipynb    # Análisis completo paso a paso
├── data/
│   ├── tienda_1.csv             # Datos tienda 1
│   ├── tienda_2.csv             # Datos tienda 2
│   ├── tienda_3.csv             # Datos tienda 3
│   └── tienda_4.csv             # Datos tienda 4
├── images/                      # Visualizaciones e imágenes
│   ├── banner.png
│   ├── facturacion_porcentaje.png
│   └── ...
├── README.md                    # Este documento
└── requirements.txt             # Dependencias del proyecto
```

## 🧹 Proceso de Limpieza de Datos

El proceso de preparación de datos incluyó:

1. **Importación y unificación de datos**
   - Carga de 4 archivos CSV (uno por tienda)
   - Añadido de identificador de tienda
   - Concatenación en un único DataFrame

2. **Normalización de columnas**
   - Remoción de acentos con `unidecode`
   - Conversión a minúsculas
   - Reemplazo de espacios por guiones bajos
   - Estandarización de nombres (lat → latitud, lon → longitud)

3. **Normalización de datos**
   - Estandarización del formato de texto (mayúsculas/minúsculas)
   - Eliminación de espacios en blanco
   - Conversión de fechas al formato datetime
   - Optimización de tipos de datos (categorías)

4. **Validación de calidad**
   - Verificación de duplicados (ninguno encontrado)
   - Comprobación de valores nulos (100% completos)
   - Confirmación de consistencia en tipos de datos

## 📊 Análisis y Visualizaciones

El análisis se estructuró en cuatro áreas clave:

### 1. Ingresos Totales por Tienda

![Facturación por tienda](https://raw.githubusercontent.com/username/AluraStoreLatam/main/images/facturacion_porcentaje.png)

**Hallazgos:**
- Tienda 1: 26.2% (₱1,150,880,400)
- Tienda 2: 25.4% (₱1,116,343,500)
- Tienda 3: 25.0% (₱1,098,019,600)
- Tienda 4: 23.4% (₱1,038,375,700)

### 2. Ventas por Categoría de Producto

![Categorías por tienda](https://raw.githubusercontent.com/username/AluraStoreLatam/main/images/categorias_tienda.png)

**Hallazgos:**
- Las categorías más populares son consistentes entre tiendas
- Muebles y Electrónicos lideran ventas en todas las tiendas
- No hay disparidad significativa en mixtura de productos

### 3. Calificaciones de Clientes

![Calificaciones promedio](https://raw.githubusercontent.com/username/AluraStoreLatam/main/images/calificaciones_promedio.png)

**Hallazgos:**
- Tienda 1: 3.98/5.0
- Tienda 2: 4.04/5.0
- Tienda 3: 4.05/5.0
- Tienda 4: 4.00/5.0

### 4. Productos Top y Flop por Tienda

![Productos más y menos vendidos](https://raw.githubusercontent.com/username/AluraStoreLatam/main/images/productos_top_flop.png)

**Productos más vendidos:**
- Tienda 1: TV LED UHD 4K (60 unidades)
- Tienda 2: Iniciando en Programación (65 unidades)
- Tienda 3: Kit de Bancas (57 unidades)
- Tienda 4: Cama Box (62 unidades)

**Productos menos vendidos:**
- Tienda 1: Auriculares con Micrófono (33 unidades)
- Tienda 2: Juego de Mesa (32 unidades)
- Tienda 3: Bloques de Construcción (35 unidades)
- Tienda 4: Guitarra Eléctrica (33 unidades)

### 5. Costos de Envío

![Costos de envío](https://raw.githubusercontent.com/username/AluraStoreLatam/main/images/costos_envio.png)

**Hallazgos:**
- Tienda 1: ₱26,018.61 (promedio)
- Tienda 2: ₱25,216.24 (promedio)
- Tienda 3: ₱24,805.68 (promedio)
- Tienda 4: ₱23,459.46 (promedio)

## 🔍 Hallazgos Clave

1. **Equilibrio en facturación:** La diferencia entre la tienda con mayor facturación (Tienda 1) y la de menor (Tienda 4) es de solo 2.8%, lo que indica estabilidad en el desempeño financiero.

2. **Consistencia en satisfacción del cliente:** Todas las tiendas mantienen calificaciones promedio por encima de 3.9/5.0, sin disparidades significativas.

3. **Distribución homogénea de categorías:** No hay diferencias notables en la distribución de categorías de productos vendidos entre tiendas.

4. **Costos logísticos optimizados:** Los costos de envío son proporcionales a las ventas en todas las tiendas.

## 📝 Conclusiones y Recomendaciones

**Conclusión principal:** Tras analizar de manera exhaustiva el desempeño de las cuatro tiendas Alura Store, no se identificaron indicadores que justifiquen el cierre de ninguna de ellas. Todas las tiendas muestran niveles de rendimiento equilibrados tanto en ingresos como en satisfacción del cliente.

**Recomendaciones:**

1. **Mantener las cuatro tiendas operativas:** Dado su desempeño estable, se recomienda continuar con todas las tiendas.

2. **Explorar alternativas de financiamiento:** Para el nuevo emprendimiento, considerar otras fuentes de capital como préstamos o inversores, preservando la red actual de tiendas.

3. **Optimizar el rendimiento actual:** En lugar de cerrar una tienda, explorar mejoras operativas para aumentar márgenes de ganancia.

4. **Estandarizar mejores prácticas:** Compartir estrategias exitosas entre las tiendas para mejorar el rendimiento general.

## 🤝 Cómo Contribuir

¡Las contribuciones son bienvenidas! Sigue estos pasos:

1. **Fork** el repositorio
2. **Clona** tu fork: `git clone https://github.com/tu-usuario/AluraStoreLatam.git`
3. **Crea** una rama para tu contribución: `git checkout -b nueva-funcionalidad`
4. **Realiza** tus cambios y documéntalos
5. **Commit** con mensajes descriptivos: `git commit -m "Agrega análisis de temporalidad"`
6. **Push** a tu fork: `git push origin nueva-funcionalidad`
7. **Envía** un Pull Request

### Normas de contribución
- Sigue las convenciones de estilo del código existente
- Documenta cualquier función nueva
- Actualiza el README si añades nuevas características
- Incluye pruebas para nuevas funcionalidades

## 📚 Referencias y Recursos

- [Challenge original de Alura Latam](https://www.aluracursos.com/)
- [Documentación de Pandas](https://pandas.pydata.org/docs/)
- [Guía de visualización con Seaborn](https://seaborn.pydata.org/tutorial.html)
- [Matplotlib: Visualización en Python](https://matplotlib.org/stable/index.html)
- [Guía de análisis exploratorio de datos](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)

## 👤 Autora

**Marely**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue.svg)](https://www.linkedin.com/in/tu-perfil/)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-lightgrey.svg)](https://github.com/tu-usuario)

---

*Este proyecto fue desarrollado como parte del Challenge de Data Science de Alura Latam, 2025.*


