---
title: Isolashes V1
published: 2024-08-29
description: 'Landing Web App para la empresa Isolashes. Mostrando los servicios que ofrece la empresa, sistemas de citas y tienda virtual.'
image: './cover-landing.png'
tags: [NestJS, Prisma, ZenStack, NextJS, React, TailwindCSS, NextAuth, PostgreSQL]
category: 'Proyecto'
draft: false
---

# Isolashes V1

Isolashes es una Landing Web App para la empresa Isolashes, salón y academia de pestañas. Esta aplicación web cuenta con dos versiones, una en NextJS y otra en Astro que es la versión en linea, ver [aquí](/post/isolashes-v2).

La versión de NextJS fue la primera versión de la aplicación, la cual fue creada con NextJS, utilizando MongoDB como motor de base de datos. Esta cuenta con un servidor en NestJS, el cual se encarga de manejar las peticiones del cliente y de la base de datos utilizando [Prisma](https://www.prisma.io/) con [PostgresSQL](https://www.postgresql.org/) con [ZenStack](https://zenstack.dev/) como toolkit de desarrollo

La versión de Astro es la segunda versión de la aplicación, la cual fue segmentada en dos aplicaciones, una para la Landing y otra para la Tienda Virtual, la cual se mantuvo en NextJS pero se le realizaron cambios a la interfaz gráfica y al servidor.

## Landing Web App

Mostrando los servicios que ofrece la empresa, sistemas de citas y tienda virtual. Esta aplicación fue creada con [NextJS](https://nextjs.org/), [React](https://reactjs.org/) y [TailwindCSS](https://tailwindcss.com) y [NextAuth](https://next-auth.js.org/).

La aplicación web permite a los usuarios ver los servicios que ofrece la empresa, agendar citas, ver los productos de la tienda virtual y realizar compras. Los usuarios pueden registrarse y autenticarse utilizando NextAuth, el cual permite autenticación con múltiples proveedores, como Google, Facebook, Twitter, etc.

### Demo de la aplicación

<iframe width="100%" height="500" src="https://www.youtube.com/embed/k5-RDm2OTKs?si=XDZ_w-8KG6kdrw3i" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Dashboard de administrador Web App

Permite a los administradores de la empresa ver las citas agendadas, los productos vendidos y los usuarios registrados. Esta aplicación fue creada con [NextJS](https://nextjs.org/), [React](https://reactjs.org/) y [TailwindCSS](https://tailwindcss.com) y [NextAuth](https://next-auth.js.org/).

Permite también editar los servicios que ofrece la empresa, los productos de la tienda virtual y los usuarios registrados. Acceder a todas las ordenes de compra, facturas, datos de los clientes y manipular el contenido de la landing mediante una interfaz gráfica amigable.

### Demo de la aplicación

<iframe width="100%" height="500" src="https://www.youtube.com/embed/bU9_606o5Xs?si=LitPkQVSnH4NA8BV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Demo de la integración del dashboard con la landing

Aquí se muestra la integración de la landing con el dashboard, donde se puede ver la actualización en tiempo real de los servicios y productos de la empresa.

<iframe width="100%" height="500" src="https://www.youtube.com/embed/WeL7IJxf-0Q?si=aAjf__HfDzA4unvn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Arquitectura de la aplicación

La aplicación quedó con un diseño bastante monolítico, donde se maneja todo en un solo servidor, tanto la landing como el dashboard. Se utilizó un servidor en NestJS, el cual se encarga de manejar las peticiones del cliente y de la base de datos utilizando Prisma con PostgresSQL con ZenStack como toolkit de desarrollo.

![Arquitectura de la aplicación](src/content/assets/arquitectura.svg)

## Listado de tecnologías utilizadas

- [NextJS](https://nextjs.org/)
- [React](https://reactjs.org/)
- [TailwindCSS](https://tailwindcss.com)
- [NextAuth](https://next-auth.js.org/)
- [MongoDB](https://www.mongodb.com/)
- [Google Cloud](https://cloud.google.com/)
- [ZenStack](https://zenstack.dev/)
- [Prisma](https://www.prisma.io/)
- [PostgresSQL](https://www.postgresql.org/)
- [NestJS](https://nestjs.com/)

## Mejoras de la aplicación

- Reducir el alto acoplamiento de la aplicación
- Reducir la complejidad del servidor para escalar en el futuro
- Mejorar la interfaz gráfica

## Repositorios de GitHub

::github{repo="nightmareVCO/isolashes-v1-landing"}
::github{repo="nightmareVCO/isolashes-v1-dashboard"}
::github{repo="nightmareVCO/isolashes-v1-server"}
