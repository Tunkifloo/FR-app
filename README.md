# FR-app
Repo for Mobile APP with face and characters recognition

## Sistema de Reconocimiento Facial con OpenCV

Este repositorio contiene una aplicación móvil desarrollada en Python utilizando Jupyter Notebook para el reconocimiento facial y de caracteres. El proyecto implementa un sistema completo de detección, análisis y reconocimiento facial usando técnicas tradicionales de visión por computadora con OpenCV.

### Descripción del Proyecto

#### Objetivo Principal
Desarrollar un sistema de reconocimiento facial que pueda:
- Detectar rostros en imágenes
- Extraer características faciales únicas
- Crear modelos de referencia para personas específicas
- Comparar nuevas imágenes contra modelos existentes
- Determinar si una imagen pertenece a la persona registrada

### Características Principales

#### 1. **Procesamiento de Imágenes**
- Conversión automática a escala de grises
- Eliminación de ruido usando filtros Gaussianos y bilaterales
- Normalización de imágenes para consistencia en el procesamiento

#### 2. **Detección de Rostros**
- Utiliza clasificadores Haar Cascade de OpenCV
- Detección automática de múltiples rostros en una imagen
- Extracción y visualización de rostros individuales
- Redimensionamiento estándar a 128x128 píxeles

#### 3. **Extracción de Características**
El sistema utiliza tres métodos complementarios para extraer características faciales:
- **Características de píxeles**: Vector de intensidades de píxeles (512 valores)
- **Histograma de intensidades**: Distribución de valores de grises (256 valores)
- **Textura LBP (Local Binary Pattern)**: Patrones de textura facial (256 valores)
- **Total**: 1024 características por rostro

#### 4. **Creación de Modelos**
- Generación automática de modelos personalizados por persona
- Almacenamiento persistente usando archivos pickle
- Configuración de umbrales de similitud personalizables
- Metadatos del modelo incluyendo nombre, imagen de referencia y método usado

#### 5. **Sistema de Reconocimiento**
- Comparación de nuevas imágenes contra modelos existentes
- Cálculo de similitud usando correlación y distancia euclidiana
- Umbral configurable para determinar coincidencias
- Visualización detallada de resultados con gráficos comparativos

#### 6. **Procesamiento por Lotes**
- Capacidad de procesar múltiples imágenes simultáneamente
- Generación de reportes de resultados por lote
- Estadísticas de coincidencias y no coincidencias

### Tecnologías Utilizadas

#### Librerías Principales
- **OpenCV (cv2)**: Procesamiento de imágenes y detección facial
- **NumPy**: Operaciones matemáticas y manejo de arrays
- **Matplotlib**: Visualización de resultados y gráficos
- **Pickle**: Serialización y almacenamiento de modelos
- **Tkinter**: Interfaz gráfica para selección de archivos

#### Algoritmos Implementados
- **Haar Cascades**: Para detección inicial de rostros
- **Local Binary Pattern (LBP)**: Para extracción de características de textura
- **Filtros Gaussianos y Bilaterales**: Para eliminación de ruido
- **Correlación de Pearson**: Para medición de similitud
- **Distancia Euclidiana**: Para comparación de vectores de características

### Funcionalidades del Sistema

#### Flujo Principal de Entrenamiento
1. **Carga de imagen de referencia** mediante interfaz gráfica
2. **Conversión y preprocesamiento** automático de la imagen
3. **Detección automática de rostros** en la imagen
4. **Extracción de características faciales** usando múltiples métodos
5. **Creación y guardado del modelo** con metadatos completos

#### Flujo de Reconocimiento
1. **Carga del modelo** previamente entrenado
2. **Selección de imagen de prueba** para comparar
3. **Procesamiento idéntico** al flujo de entrenamiento
4. **Comparación de características** usando algoritmos de similitud
5. **Decisión final** basada en umbral configurable
6. **Visualización de resultados** con gráficos comparativos

#### Funciones Auxiliares
- **Gestión de umbrales**: Modificación dinámica de sensibilidad
- **Validación de modelos**: Verificación de integridad de archivos
- **Interfaz de usuario**: Diálogos intuitivos para selección de archivos
- **Reportes detallados**: Métricas de similitud y confianza

### Estructura del Proyecto

#### Organización de Archivos