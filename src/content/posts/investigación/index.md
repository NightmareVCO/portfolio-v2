---
title: Investigación Científica
published: 2024-08-01
description: 'Comparando la eficacia de los algoritmos de búsqueda de palabras en un texto de la librería re de python.'
image: './cover.png'
tags: [Python, Re]
category: 'Investigación'
draft: false
---

# Investigación Científica

## Abstract

En esta investigación se quiere comparar el rendimiento en términos de tiempo de tres métodos de
búsqueda de palabras de la librería re de Python: findall, search y finditer. Utilizando datos cuantitativos y
partiendo de un muestreo estratificado, se tomaron distintos textos arbitrados de una determinada
categoría. Se analizaron 374 resúmenes extraídos de Scopus, se obtuvieron las 10 palabras más
repetidas, y se midió el tiempo utilizando dos métodos de medición de tiempo
distintos: timeit y perf_counter. Este proceso se repitió 10,000 veces para obtener un promedio de tiempo
fiable, lo que dio un total de 224,400,000 iteraciones. Los resultados revelan que finditer es el algoritmo
más rápido para realizar la tarea, con una diferencia del 93.51% de eficiencia según los tiempos
obtenidos al medir.

## Paper

<object data="/paper.pdf" type="application/pdf" width="100%" height="500">
  <a href="./paper.pdf">Paper de la investigación.</a>
</object>

## Poster del paper

<object data="/poster.pdf" type="application/pdf" width="100%" height="500">
  <a href="./poster.pdf">Poster del paper.</a>
</object>

## Resultados

En este estudio se ha evaluado y comparado el rendimiento en términos de tiempo de tres métodos de
búsqueda de palabras de la librería re de Python: findall, search y finditer. Con un enfoque cuantitativo
basado en un muestreo estratificado, se analizaron 374 resúmenes de Scopus para identificar las 10
palabras más repetidas y se midió el tiempo de ejecución utilizando timeit y perf_counter. Este proceso
se repitió 10,000 veces, dando un total de 224,400,000 iteraciones. Los resultados revelan que finditer es
el algoritmo más eficiente, mostrando una diferencia del 93.51% en la eficiencia según los tiempos
obtenidos.

## Repositorio de GitHub

::github{repo="nightmareVCO/solid-robot"}