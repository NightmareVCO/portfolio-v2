---
title: JMS - Temperatura y Humedad
published: 2025-03-03
description: 'Aplicación web para visualizar la temperatura y humedad de sensores comunicados por Java Message Service.'
image: './cover.png'
tags: [SpringBoot, Java, JMS, ActiveMQ, NextJS, TailwindCSS, Docker]
category: 'Practica'
draft: false
---

# JMS - Temperatura y Humedad

JMS - Temperatura y Humedad es una aplicación web para visualizar en tiempo real la temperatura y la humedad captadas por sensores, empleando Java Message Service (JMS). Gracias a su interfaz intuitiva y gráficos dinámicos, permite monitorizar los datos de forma continua y eficiente.

## Detalles de la aplicación

El servidor se desarrolló con Spring Boot, utilizando Apache ActiveMQ como broker de mensajería y PostgreSQL como sistema de persistencia. El cliente está construido en Next.js y Tailwind CSS para un diseño moderno y responsivo. Los sensores, implementados en Java, envían tramas JSON a través de JMS y el servidor retransmite los datos al cliente mediante WebSockets. Toda la solución está dockerizada y orquestada con Docker Compose, lo que facilita su despliegue en cualquier entorno.

### Funcionalidades

- Gráficos de línea en tiempo real para la temperatura de cada sensor.  
- Gráficos de línea en tiempo real para la humedad de cada sensor.  
- Actualización automática vía WebSockets.

Desarrollado en colaboración con [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/).

## Tecnologías utilizadas

- **Backend**  
  - [Spring Boot](https://spring.io/projects/spring-boot)  
  - [Java](https://www.java.com/)  
  - [JMS (Java Message Service)](https://javaee.github.io/tutorial/jms.html)  
  - [Apache ActiveMQ](https://activemq.apache.org/)  
  - [PostgreSQL](https://www.postgresql.org/)

- **Frontend**  
  - [Next.js](https://nextjs.org/)  
  - [Tailwind CSS](https://tailwindcss.com/)  
  - [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)

- **Contenedores**  
  - [Docker](https://www.docker.com/)  
  - [Docker Compose](https://docs.docker.com/compose/)

## Desarrollo de la práctica

La solución consta de tres componentes:

1. **Simulador de Endpoints (Java + JMS)**  
   - Genera **dos** hilos que envían cada minuto un JSON con la estructura:  
     ```json
     {
       "fechaGeneración": "DD/MM/YYYY HH:mm:ss",
       "IdDispositivo": <Int>,
       "temperatura": <Number>,
       "humedad": <Number>
     }
     ```  
   - Publica cada mensaje en la cola `notificacion_sensores` mediante el estándar JMS (OpenWire bajo ActiveMQ).  

2. **Servidor Spring Boot**  
   - Se subscribe a `notificacion_sensores`, persiste cada trama en PostgreSQL y, a través de WebSockets, retransmite los datos al cliente web.  

3. **Cliente Web (Next.js + TailwindCSS)**  
   - Abre una conexión WebSocket para recibir lecturas en tiempo real.  
   - Dibuja dos gráficos de línea: temperatura vs. tiempo y humedad vs. tiempo para cada sensor.  

**Despliegue:** todo se orquesta con Docker Compose, levantando contenedor de ActiveMQ, servicio Spring Boot, base de datos y frontend.

## Repositorio de GitHub

::github{repo="/nightmareVCO/advanced-web/tree/main/practica-5}