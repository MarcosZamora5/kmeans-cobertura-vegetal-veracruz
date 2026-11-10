# Sensibilidad de un indicador de cobertura vegetal basado en K-Means con paleta de colores de referencia

Repositorio oficial con el código y conjunto de datos del artículo:  
**"Sensibilidad de un indicador de cobertura vegetal basado en K-Means con paleta de colores de referencia: evaluación en imágenes satelitales de parcelas agrícolas de Veracruz"**

**Autores:** Dariana de los Ángeles Martínez Zúñiga, Marcos Francisco Zamora Reyes, Virginia Lagunes Barradas  
**Institución:** Tecnológico Nacional de México / Instituto Tecnológico Superior de Xalapa (ITSX)  
**Línea temática:** Ciencia de datos, Big Data y analítica predictiva

---

## 📌 Descripción del proyecto
Este repositorio implementa un flujo reproducible en Python para estimar y comparar la proporción de cobertura vegetal activa en tres zonas agrícolas de Veracruz (**Coatepec**, **Actopan** y **Valle de Perote**) a partir de imágenes satelitales RGB de acceso público:
1. **Paleta de referencia común:** Ajuste de un único modelo `K-Means` ($K = 5$, `random_state = 42`) sobre una muestra combinada de 90,000 píxeles (30,000 por zona).
2. **Clasificación espectral:** Cálculo del índice de exceso de verde ($\text{ExG} = 2G - R - B$) y brillo medio por centroide dentro de regiones de interés (ROI) agrícolas.
3. **Procesamiento morfológico (OpenCV):** Apertura ($5 \times 5$) y cierre elíptico ($7 \times 7$) seguidos de extracción de contornos (`findContours`) para contabilizar regiones continuas ($\ge 0.5\%$ del área).
4. **Análisis de sensibilidad:** Evaluación de estabilidad del indicador ante cambios en la asignación de clústeres (configuración base vs. alternativa) y comparación en el espacio de color **CIE Lab** y mediante el **coeficiente de silueta**.

---

## 📂 Estructura del repositorio
* `C_Variaciones_Cultivos.ipynb`: Cuaderno de Jupyter ejecutable con todo el pipeline de preprocesamiento, modelado, tablas de resultados, gráficas y pruebas de sensibilidad.
* `Coatepec.png`, `Actopan.png`, `Perote.png`: Imágenes satelitales analizadas (Zonas 1, 2 y 3).
* `requirements.txt`: Bibliotecas de Python necesarias para reproducir el entorno.

---

## 🚀 Instalación y reproducibilidad
1. Clonar este repositorio:
   ```bash
   git clone [https://github.com/MarcosZamora5/kmeans-cobertura-vegetal-veracruz.git](https://github.com/MarcosZamora5/kmeans-cobertura-vegetal-veracruz.git)
   cd kmeans-cobertura-vegetal-veracruz
