---
title: Mockify
published: 2025-03-13
description: 'Aplicación web para crear mock de APIs REST, proyectos y más.'
image: './cover.webp'
tags: [SpringBoot, Redis, HAProxy, NextJS, TailwindCSS, Docker]
category: 'Proyecto'
draft: false
---

# Mockify

Mockify es una aplicación web para crear mock de APIs REST, proyectos y más. Los mocks creados pueden ser utilizados para pruebas de software, desarrollo de software, entre otros. Es una aplicación cliente servidor, donde el servidor se encarga de manejar la lógica de negocio y la base de datos, y el cliente se encarga de mostrar la información al usuario y de enviar los datos al servidor. 


## Detalles de la aplicación

El servidor fue desarrollado en SpringBoot, utilizando Redis como base de datos y HAProxy como balanceador de carga. El cliente fue desarrollado en NextJS, utilizando TailwindCSS para el diseño. Toda la aplicación se encuentra dockerizada, permitiendo una fácil instalación y despliegue en cualquier servidor. Asi mismo, la configuración del proxy inverso para apache se encuentra en el repositorio de GitHub.

Los mocks puede ser personalizados con diferentes respuestas(xml, html, json), headers, status code, delay, protección con jwt y más. Los mocks pueden ser creados por cualquier usuario, pero solo los administradores pueden eliminarlos. Los mocks están relacionados con proyectos, los cuales pueden ser creados por cualquier usuario, pero solo los administradores pueden eliminarlos. Los usuarios pueden ser administradores o miembros, los cuales pueden crear mocks y proyectos, pero solo los administradores pueden eliminarlos.

La aplicación cuenta con las siguientes funcionalidades:

- Gestión de proyectos.
- Gestión de mocks.
- Gestión de usuarios.
- Gestión de roles.
- Autenticación de usuarios.
- Comunidad de proyectos.

La aplicación fue desarrollada en conjunto con [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/)

## Demo de la aplicación

<iframe width="100%" height="500" src="https://www.youtube.com/embed/4V_lEfckXC4?si=eabLpfq8wfBbX4Lg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Listado de tecnologías

- [SpringBoot](https://spring.io/projects/spring-boot)
- [Redis](https://redis.io/)
- [HAProxy](http://www.haproxy.org/)
- [NextJS](https://nextjs.org/)
- [TailwindCSS](https://tailwindcss.com)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [JWT](https://jwt.io/)
- [Apache](https://httpd.apache.org/)
- [PostgreSQL](https://www.postgresql.org/)

### Repositorio de GitHub

::github{repo="nightmareVCO/mockify"}
