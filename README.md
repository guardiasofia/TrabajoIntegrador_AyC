# 🗺️ Optimización de Circuitos Turísticos en Concordia

Este repositorio contiene el desarrollo de un trabajo práctico para la asignatura **Algoritmos y Complejidad** de la **Licenciatura en Sistemas** (Facultad de Ciencias de la Administración). El proyecto aborda el problema de optimización de rutas turísticas en la ciudad de **Concordia, Entre Ríos**, aplicando técnicas de investigación de operaciones y heurísticas para la resolución del **Problema del Agente Viajero con Ventanas de Tiempo (TSP-TW)**.

## 📋 Tabla de Contenidos

- [Descripción del Problema](#descripción-del-problema)
- [Metodología](#metodología)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Resultados](#resultados)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Cómo Ejecutar](#cómo-ejecutar)
- [Contribuciones](#contribuciones)
- [Autores](#autores)

## 📝 Descripción del Problema

El objetivo es diseñar un circuito turístico óptimo que visite un conjunto de puntos de interés en la ciudad de Concordia. El problema debe considerar:

- **Tiempos de viaje** entre los puntos, calculados a partir de un grafo de calles reales (OpenStreetMap).
- **Ventanas de tiempo** (horarios de apertura y cierre) de cada lugar.
- **Tiempo de visita** requerido en cada punto.
- Encontrar la ruta que minimice el tiempo total de recorrido, respetando todos los horarios.

## 🛠️ Metodología

La solución se aborda en varias etapas:

1.  **Adquisición de Datos**: Se utiliza la librería `osmnx` para descargar el grafo de calles de Concordia y calcular los tiempos de viaje entre todos los pares de puntos turísticos.
2.  **Generación de la Ruta Inicial**: Se implementa una **heurística constructiva de inserción** para obtener una primera solución factible.
3.  **Mejora Local**: Se aplica el algoritmo **2-opt** para optimizar la ruta obtenida.
4.  **Metaheurística**: Se implementa una **Búsqueda Tabú** para explorar el espacio de soluciones, permitiendo empeoramientos temporales para escapar de óptimos locales.
5.  **Análisis y Visualización**:
    - Visualización de la ruta óptima sobre el mapa de calles.
    - Generación de gráficos comparativos para analizar el rendimiento de las diferentes heurísticas (tiempo total, desglose de tiempos de manejo, espera y visita).

## 🚀 Tecnologías Utilizadas

- **Python 3**: Lenguaje de programación principal.
- **osmnx**: Descarga y manejo de grafos de calles desde OpenStreetMap.
- **networkx**: Manipulación y análisis de grafos.
- **matplotlib**: Visualización de rutas y gráficos.
- **pandas / numpy**: Manejo y análisis de datos.

## 📊 Resultados

Se compararon tres enfoques para resolver el problema:

| Heurística       | Tiempo Total (min) | Mejora vs Inserción |
| :--------------- | :----------------: | :-----------------: |
| Inserción        | 426                | -                   |
| 2-opt            | 417                | -2.2%               |
| Búsqueda Tabú    | 410                | -3.7%               |

La **Búsqueda Tabú** logró la mejor solución, reduciendo el tiempo total del circuito en un 3.7% en comparación con la solución constructiva inicial.

### Mapa de la Ruta Óptima

![Circuito Turístico Óptimo](ruta_optima.png)

### Gráficos Comparativos

![Comparación de Heurísticas](comparativa_metricas.png)

## 📂 Estructura del Proyecto

```
.
├── INTEGRADOR_AyC (3).ipynb  # Notebook principal con todo el código.
├── README.md                 # Este archivo.
└── assets/                   # (Opcional) Carpeta para imágenes.
    ├── ruta_optima.png
    └── comparativa_metricas.png
```

## 🧑‍💻 Cómo Ejecutar

1.  **Clonar el repositorio**:
    ```bash
    git clone https://github.com/tu-usuario/tu-repositorio.git
    cd tu-repositorio
    ```

2.  **Instalar las dependencias**:
    El notebook incluye una celda inicial para instalar las librerías necesarias. Si prefieres hacerlo manualmente:
    ```bash
    pip install osmnx networkx matplotlib numpy pandas
    ```

3.  **Ejecutar el Notebook**:
    Abre el archivo `INTEGRADOR_AyC.ipynb` en un entorno Jupyter (como Google Colab o Jupyter Notebook) y ejecuta las celdas en orden.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si encuentras un error o tienes una sugerencia para mejorar el proyecto, por favor, abre un "Issue" o envía un "Pull Request".

## 👨‍🎓 Autores

- **Martina Fernandez Risso**
- **Sofía Guardia**
- **Eduardo Juarez**
- **Joaquín Pralong**

---

*Proyecto desarrollado para la asignatura Algoritmos y Complejidad - Licenciatura en Sistemas - FCAyF - 2025.*
