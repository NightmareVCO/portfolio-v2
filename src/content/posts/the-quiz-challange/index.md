---
title: The Quiz Challenge
published: 2024-11-27
description: 'Dashboard Interactivo de Minería de Datos con Modelo Descriptivo en Clusters.'
image: './cover.png'
tags: [Tableau, Python, Juyper Notebook, Scikit-Learn, NLTK, Pandas, YouTube API]
category: 'Proyecto'
draft: false
---

# Dashboard Interactivo – The Quiz Challenge

[Dashboard Interactivo de The Quiz Challenge](https://public.tableau.com/app/profile/vladimir.curiel/viz/TheQuizChallenge-YouTubeChannel/Vistas-Pgina1) es una solución de minería de datos descriptiva que combina un modelo de clustering con un portal visual en Tableau. El objetivo es ayudar al canal de YouTube “The Quiz Challenge” a descubrir patrones en sus métricas (vistas, suscripciones, comentarios, likes/dislikes) y tomar decisiones informadas sobre qué tipo de contenido producir.

## Detalles del proyecto

- **Fuente de datos**  
  - Conjunto original de estadísticas de YouTube (vistas, suscriptores, comentarios, likes/dislikes) agrupado en carpetas por parámetro.  
  - Exploración de fuentes externas de métricas de canales de YouTube para enriquecer el dataset (p.ej. demografía de audiencia, keywords trending)

- **Dashboard en Tableau**  
  - Preparación y transformación de datos en Tableau Prep (unión de fuentes, limpieza de valores faltantes, creación de campos calculados para cuartiles de vistas y grupos horarios).  
  - Visualizaciones interactivas:  
    - Líneas de tiempo de vistas y suscripciones.  
    - Histogramas de duración y distribución por categoría.  
    - Filtros por cuartil de vistas, grupo horario y cluster asignado.  
    - Panel de detalle por video con métricas y etiquetas.  
  - Publicación en Tableau Public con enlace público para stakeholders.

- **Modelo descriptivo en clusters**  
  - **Entorno**: Python 3 en Jupyter Notebook.  
  - **Preprocesamiento**: tokenización de títulos y descripciones con NLTK, limpieza de stopwords y lematización.  
  - **Vectorización**: TF-IDF para contenido textual y normalización de métricas numéricas (vistas, likes/dislikes, duración).  
  - **Algoritmo**: K-Means (selección de k basada en curva de codo y coeficiente de silhouette) y DBSCAN como verificación de densidad.  
  - **Evaluación**: Silhouette Score, Davies–Bouldin Index y análisis de cohesión vs. separación para validar calidad de clusters.  
  - **Interpretación**: asignación de etiquetas descriptivas a cada cluster (p.ej. “videos cortos de trivia”, “quizzes extensos de temática X”) para guiar la estrategia de contenido.

## Tecnologías utilizadas

- **Visualización:** Tableau Desktop & Tableau Public  
- **Análisis & Modelado:**  
  - Python 3  
  - Jupyter Notebook  
  - Pandas, NumPy  
  - Scikit-Learn (K-Means, DBSCAN, métricas de clustering)  
  - NLTK (tokenización, lematización, stopwords)  
- **Documentación:** Markdown en `README.md` describiendo flujo de ETL, decisiones de modelado y hallazgos.

## Desarrollo del proyecto

1. **Exploración de datos**  
   - Carga de CSVs originales y revisión de calidad de datos.  
   - Identificación de métricas faltantes y normalización de formatos de fecha.

2. **Preparación y ETL en Tableau Prep**  
   - Unión de fuentes, limpieza y creación de campos (cuartiles, grupos horarios).  
   - Exportación de extractos `.hyper` para conexión en Tableau Desktop.

3. **Modelado en Jupyter Notebook**  
   - Preprocesamiento de texto con NLTK y vectorización TF-IDF.  
   - Ejecución de K-Means y análisis de métricas para elegir k.  
   - Visualización de clusters en 2D con PCA para ver separabilidad.

4. **Creación del dashboard**  
   - Conexión a los datos modelados (incluyendo etiqueta de cluster) en Tableau Desktop.  
   - Diseño de hojas y dashboard final con acciones de filtro y resaltado.  
   - Publicación en Tableau Public para acceso público, con credenciales de visualización.

El proyecto fue desarrollado en conjunto con [Natasha López](https://github.com/Natashalopez05).

## Dashboard Interactivo

<div class='tableauPlaceholder' id='viz1733936962257' style='position: relative'><noscript><a href='#'><img alt='Vistas Página #1: Celebreación, Duración, Categoría, Cuartil &amp; Grupo Horario ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Th&#47;TheQuizChallenge-YouTubeChannel&#47;Vistas-Pgina1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='TheQuizChallenge-YouTubeChannel&#47;Vistas-Pgina1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Th&#47;TheQuizChallenge-YouTubeChannel&#47;Vistas-Pgina1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1733936962257');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';} else { vizElement.style.width='100%';vizElement.style.height='2627px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>

## Listado de tecnologías utilizadas

- [Tableau](https://www.tableau.com/)
- [Python](https://www.python.org/)
- [Jupyter Notebook](https://jupyter.org/)
- [Scikit-Learn](https://scikit-learn.org/)
- [NLTK](https://www.nltk.org/)
- [YouTube API](https://developers.google.com/youtube/v3)

## Repositorio de GitHub

::github{repo="nightmareVCO/the-quiz-challenge"}