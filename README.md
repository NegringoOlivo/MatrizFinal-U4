# 🔴 Evaluación Avanzada: Análisis Térmico de Sensores Bidimensionales 🌡️🌱

¡Bienvenidos al reto final de matrices! 🚀 Este ejercicio evaluará tu capacidad para recorrer estructuras multidimensionales complejas, manejar los límites de los índices y extraer información crítica a partir de un conjunto de datos brutos.

---

## 📋 Descripción del Problema

Un sistema de monitoreo en un invernadero registra la temperatura a través de una red de sensores distribuidos en forma de cuadrícula. Los datos se almacenan en una matriz `N x M` (donde `N` son las filas y `M` las columnas). Cada celda contiene un número entero que representa la temperatura en grados Celsius de ese sector específico.

Tu objetivo es desarrollar un algoritmo que analice esta matriz y genere un reporte automatizado con tres puntos críticos de información.

---

## 🎯 Requisitos del Algoritmo

Tu programa debe recibir la matriz de temperaturas y cumplir **estrictamente** con las siguientes tres tareas:

### 1. 📍 Búsqueda de Extremos (Coordenadas)
Encuentra la temperatura **más alta** y la **más baja** de todo el invernadero. 
* **Salida esperada:** El valor de la temperatura y las coordenadas exactas `(fila, columna)` de ambos puntos. Si el valor extremo se repite, devuelve las coordenadas del primero que encuentres.

### 2. 🚨 Detección de Zonas Críticas (Análisis de Sub-matrices)
Una "Zona Crítica" se define como un bloque adyacente de **2x2** sensores (una sub-matriz de 2 filas por 2 columnas) donde **todas** las celdas registran una temperatura igual o superior a `35°C`.
* **Salida esperada:** El algoritmo debe buscar en toda la matriz e imprimir las coordenadas de la esquina superior izquierda `(fila, columna)` de la primera Zona Crítica encontrada. Si no existe ninguna, debe imprimir: `"✅ Estado Normal: Sin zonas críticas"`.

### 3. 🌊 Suavizado de Datos Térmicos (Filtro de Convolución Básico)
Los sensores a veces tienen picos de error. Para limpiar los datos, debes crear y devolver una **nueva matriz** del mismo tamaño `N x M` aplicando un "suavizado".
* **Regla:** El valor de cada celda en la nueva matriz será el **promedio entero** (sin decimales) de la celda original y sus vecinos directos (arriba, abajo, izquierda, derecha). 
* ⚠️ **Cuidado con los bordes:** Si una celda está en una esquina o borde, naturalmente tendrá menos vecinos. Tu algoritmo no debe romperse al intentar acceder a índices que no existen (fuera de los límites de la matriz).

---

## 📥 Ejemplo de Entrada y Salida

**Matriz de Entrada (Ejemplo de 4x5):**
```text
[
  [22, 24, 35, 36, 28],
  [23, 25, 37, 35, 30],
  [21, 24, 26, 29, 31],
  [20, 22, 23, 25, 27]
]
