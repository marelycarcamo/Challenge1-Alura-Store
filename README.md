
Este repositorio contiene un proyecto de análisis de datos sobre la cadena **Alura Store**, con el objetivo de determinar si es conveniente cerrar alguna de sus cuatro tiendas.

---

## 📚 Contenido

1. [Descripción del Proyecto](#descripción-del-proyecto)  
2. [Requisitos e Instalación](#requisitos-e-instalación)  
3. [Estructura de Archivos](#estructura-de-archivos)  
4. [Pasos de Limpieza de Datos](#pasos-de-limpieza-de-datos)  
5. [Análisis y Visualizaciones](#análisis-y-visualizaciones)  
6. [Conclusiones](#conclusiones)  
7. [Cómo contribuir](#cómo-contribuir)  
8. [Referencias y Créditos](#referencias-y-créditos)  

---

## Descripción del Proyecto

Durante este desafío, ayudamos al Sr. Juan a decidir si debe cerrar alguna de las cuatro tiendas de su cadena **Alura Store** antes de iniciar un nuevo emprendimiento. Analizamos:

- Ingreso total por tienda  
- Ventas por categoría  
- Valoración media de clientes  
- Productos más y menos vendidos  
- Costo promedio de envío  

---

## Requisitos e Instalación

1. **Clonar este repositorio**  
   ```bash
   git clone https://github.com/tu_usuario/AluraStoreLatam.git
   cd AluraStoreLatam
   ````


2. **Crear un entorno virtual**
   ```bash
   python3.11 -m venv venv
   source venv/bin/activate    # macOS/Linux
   venv\Scripts\activate       # Windows
    ```

3. **Instalar dependencias**
   ```
    pip install -r requirements.txt
    ```
  
   **Contenido de requirements.txt:**
    ```bash
      pandas==2.2.2
      seaborn==0.13.2
      matplotlib==3.10.0
      unidecode
    ```

---

## Estructura de archivos

  ```bash
  ├── AluraStoreLatam.ipynb    # Notebook con el análisis paso a paso
  ├── README.md                # Este archivo
  ├── requirements.txt         # Dependencias del proyecto
  └── data/
      ├── tienda_1.csv
      ├── tienda_2.csv
      ├── tienda_3.csv
      └── tienda_4.csv
  ```

---

## Pasos de Limpieza de Datos

- Importar librerías y revisar versiones
- Cargar CSVs y concatenar en `df_tiendas`
- Renombrar columnas
- Uso de unidecode para eliminar acentos
- Convertir a minúsculas y reemplazar espacios por `_`
- Reemplazos personalizados (`_de_`,`_del_`, `lat` → `latitud`, `lon` → `longitud`)
- Normalizar valores de texto
- Eliminar espacios en blanco
- Convertir a minúsculas (`producto`, `categoria`, `metodo_pago`, `tienda`)
- Convertir a “Title Case” (`vendedor`, `lugar_compra`)
- Convertir columnas a tipo `category`
- Verificar duplicados y nulos

---

## Análisis y Visualizaciones

- Ingreso total por tienda
  - Gráfico circular ordenado de mayor a menor.
- Ventas por categoría
  - Gráfico de barras apiladas para comparar categorías.
- Valoración media por tienda
  - Gráfico de barras con etiquetas de decimales.
- Productos más y menos vendidos
  - Tabla resumen y gráfico de barras.
- Costo promedio de envío
  - Gráfico de barras horizontales.

 

>**Tip didáctico:**
>- "Usa siempre `sns.set_style("whitegrid")` antes de graficar".
>- "Ajusta márgenes con `plt.tight_layout()`".
>- "Formatea valores con `f"{valor:.1f}"` o `"{:,.0f}".format(valor)`".


---

## Conclusiones
>Basándonos en los datos, no se recomienda cerrar ninguna tienda, pues todas muestran un desempeño equilibrado en ingresos, satisfacción y eficiencia.


---

## Cómo contribuir

- Haz un fork de este repositorio.
- Crea una rama nueva: git checkout `-b mi-nueva-funcionalidad`.
- Realiza tus cambios y haz commit: `git commit -m "Agrego X mejora"`.
- Envía un pull request.

---

## Referencias y Créditos
- Challenge original de Alura Latam
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Documentation](https://seaborn.pydata.org/)
- [Matplotlib Documentation](https://matplotlib.org/stable/index.html)
  


