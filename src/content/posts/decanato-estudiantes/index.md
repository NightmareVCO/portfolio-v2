---
title: Vida Estudiantil [En construcción]
published: 2025-03-14
description: 'Página web para el Decanato de Estudiantes de la PUCMM.'
image: './cover.png'
tags: [WordPress, Astro, SCSS, RSS, SwiperJS, Bootstrap, MySQL, Docker]
category: 'Proyecto'
draft: false
---

# Vida Estudiantil - Decanato de Estudiantes (PUCMM)

[Vida Estudiantil](https://decanato-estudiante.eict.ce.pucmm.edu.do/) es una página web para el Decanato de Estudiantes de la PUCMM. La página web tiene como objetivo permitir a los estudiantes ver información sobre los servicios que ofrece el Decanato de Estudiantes, así como también ver noticias, eventos, servicios, beneficios, asociaciones, clubes y comités relacionados con la vida estudiantil.

Del mismo modo, la página web permite a los estudiantes pertenecientes a las asociaciones, clubes y comités, ver información sobre su respectiva asociación, club o comité, crear eventos para los estudiantes, ver noticias relacionadas, ver beneficios y servicios, entre otros.

Se pueden explorar todos los grupos extra-curriculares, como lo pueden ser los grupos de arte y cultura, deportes, religiosos, entre otros. Además, se pueden ver los eventos, noticias, beneficios y servicios de cada grupo extra-curricular.

Se aprovecha el protocolo RSS para la obtención de noticias provenientes de Prensa PUCMM, permitiendo a los estudiantes ver las noticias más recientes de la universidad. Del mismo modos los videos de la página web son obtenidos de la plataforma de YouTube de la PUCMM, PUCMM TV mediante RSS.


## Detalles de la aplicación

Como servidor de la página web se utilizó WordPress, el cual se encarga de manejar la creación de eventos nuevos y el almacenamiento de la base de datos. Para el frontend se utilizó Astro, el cual se encarga de mostrar la información al usuario y de enviar los datos al backend. Para el diseño de la página se utilizó SCSS en conjunto con Bootstrap y SwiperJS para los sliders.

Toda la aplicación se encuentra dockerizada, permitiendo una fácil instalación y despliegue en cualquier servidor.

La aplicación fue desarrollada bajo la supervisión del Ing. [Freddy Peña](https://www.linkedin.com/in/fred-pena/?locale=es_ES), profesor de la escuela de Ingeniería de Computación y Telecomunicaciones de la PUCMM.

## Listado de tecnologías

- [WordPress](https://wordpress.org/)
- [Astro](https://astro.build/)
- [SCSS](https://sass-lang.com/)
- [SwiperJS](https://swiperjs.com/)
- [Bootstrap](https://getbootstrap.com/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)


### Repositorio de GitHub

::github{repo="nightmareVCO/vida-universitaria"}
