---
title: JMS - Temperatura y Humedad
published: 2025-03-03
description: 'Aplicación web para visualizar la temperatura y humedad de sensores comunicados por Java Message Service.'
image: './cover.png'
tags: [SpringBoot, Java, JMS, ActiveMQ, NextJS, TailwindCSS, Docker]
category: 'Proyecto'
draft: false
---

# JMS - Temperatura y Humedad

JMS - Temperatura y Humedad es una aplicación web para visualizar la temperatura y humedad de sensores comunicados por Java Message Service. Permite visualizar la temperatura y humedad de los sensores en tiempo real mediante un vistoso gráfico.


## Detalles de la aplicación


El servidor fue desarrollado en SpringBoot, utilizando ActiveMQ como servidor de mensajería y base de datos. El cliente fue desarrollado en NextJS, utilizando TailwindCSS para el diseño. Del mismo modos los sensores fueron desarrollados en Java, utilizando JMS para la comunicación con el servidor. Toda la aplicación se encuentra dockerizada, permitiendo una fácil instalación y despliegue en cualquier servidor.

La aplicación cuenta con las siguientes funcionalidades:

- Visualización de la temperatura en tiempo real.
- Visualización de la humedad en tiempo real.

La aplicación fue desarrollada en conjunto con [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/)

## Listado de tecnologías

- [SpringBoot](https://spring.io/projects/spring-boot)
- [Java](https://www.java.com/)
- [JMS](https://javaee.github.io/tutorial/jms.html)
- [ActiveMQ](https://activemq.apache.org/)
- [NextJS](https://nextjs.org/)
- [TailwindCSS](https://tailwindcss.com)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [PostgreSQL](https://www.postgresql.org/)

### Repositorio de GitHub

::github{repo="nightmareVCO/advanced-web/tree/main/practica-5"}
