---
title: Bienestar Estudiantil [En Desarrollo]
published: 2025-05-04
description: 'Página web para el Decanato de Estudiantes de la PUCMM.'
image: './cover.png'
tags: [WordPress, Astro, SCSS, RSS, Bootstrap]
category: 'Proyecto'
draft: false
---

# Bienestar Estudiantil – Decanato de Estudiantes (PUCMM)

[Bienestar Estudiantil](https://bienestar-estudiantil.pucmm.edu.do/) es la plataforma web oficial del Decanato de Estudiantes de la PUCMM, diseñada para centralizar y mostrar de forma clara todos los servicios, beneficios, asociaciones, clubes y comités disponibles para la comunidad estudiantil. Además, facilita la gestión de eventos y la publicación de contenido dinámico.


### Objetivos principales

- Diseñar y desarrollar una web que muestre servicios, beneficios, grupos estudiantiles y sus actividades.  
- Integrar una plataforma de gestión de contenido (BackOffice) para publicar y editar eventos directamente desde un CMS.  
- Documentar el proyecto para futuros mantenimientos y garantizar un entorno de producción seguro y controlado Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil

## Funcionalidades clave

- **Exploración de grupos estudiantiles**  
  Navega entre asociaciones, clubes y comités (arte y cultura, deportes, religiosas, etc.) mediante rutas dinámicas y sliders de imágenes que destacan su misión, visión y valores Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil

- **Gestión de eventos**  
  Visualiza todas las actividades por grupo, con título, fecha e imagen destacada, y filtra por campus o página mediante paginación Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil

- **Integración de noticias y multimedia**  
  - Noticias en tiempo real extraídas mediante REST API desde el sitio de Prensa PUCMM Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil  
  - Videos integrados mediante RSS desde la lista de reproducción de PUCMM TV en YouTube Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil

- **BackOffice con WordPress**  
  - Consumo directo de la REST API para crear, editar y eliminar entradas de actividades.  
  - Panel de administración de categorías y gestión de eventos integrado en WordPress Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil

## Seguridad y extensiones personalizadas

Para asegurar que solo peticiones fiables accedan al CMS, se desarrollaron dos plugins personalizados en PHP:

1. **Restricción de orígenes y autenticación**  
   Solo se aceptan peticiones desde el dominio autorizado, usando contraseñas de aplicación Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil  
2. **Ocultamiento de la página pública de WordPress**  
   Impide la exploración directa del sitio WordPress, exponiendo únicamente la interfaz Astro/React Informe del Proyecto del Decanato de Estudiantes, Bienestar Estudiantil

## Tecnologías utilizadas

- **Backend CMS**: WordPress (REST API, PHP, plugins custom)  
- **Frontend**: Astro (con React para fetch), SCSS, Bootstrap, SwiperJS  
- **Feeds**:  
  - Noticias: REST API de Prensa PUCMM  
  - Videos: RSS de PUCMM TV en YouTube  
- **Generación estática**: rutas dinámicas y contenidos pre-renderizados para performance y SEO  

## Desarrollo del proyecto

1. **Diseño de la estructura**: definición de esquemas de grupos y actividades.  
2. **Implementación en Astro**: componentes reutilizables, rutas dinámicas con `getStaticPaths` y pre-carga de páginas.  
3. **Integración CMS**: conexión a WordPress para gestión de eventos y categorías.  
4. **Integración de noticias y multimedia**:  
   - Consumo de la REST API de Prensa PUCMM para extraer noticias de “Vida Estudiantil”.  
   - Lectura de RSS para cargar videos de la playlist de PUCMM TV.  
5. **Feeds RSS y REST**: configuración de lectura automática y mapeo de datos en Astro/React.  
6. **Despliegue**: hosting en entorno estático, garantizando alta disponibilidad y seguridad.

**Supervisión:** Ing. Freddy Peña, Escuela de Ingeniería en Computación y Telecomunicaciones, PUCMM.

## Repositorio de GitHub

::github{repo="nightmareVCO/bienestar-estudiantil"}