---
title: Lab Reservations (Serverless)
published: 2025-03-03
description: 'Aplicación web sin servidor para gestionar solicitudes de acceso a los laboratorios serverless.'
image: './cover.png' 
tags: [SpringBoot, Java, JMS, ActiveMQ, NextJS, TailwindCSS, Docker]
category: 'Practica'
draft: false
---

# Lab Reservations

[Lab Reservations](https://polite-sopapillas-4cc193.netlify.app/) es una aplicación web sin servidor para gestionar solicitudes de acceso a los laboratorios de forma sencilla y segura. Aprovecha AWS Lambda para la lógica de negocio (implementada en Go), Netlify para el hosting del frontend y DynamoDB para la persistencia de datos. Su diseño permite registrar y consultar reservas en tiempo real, respetando las reglas de capacidad y horario.

## Detalles de la aplicación

- **Frontend**  
  - Implementado en [Astro](https://astro.build/) con componentes en [ReactJS](https://reactjs.org/) y desplegado en Netlify.  
  - Formulario de reserva (correo, nombre, ID de usuario, laboratorio, hora).  
  - Listado de reservas activas y consulta de historial por rango de fechas.

- **Lógica de negocio (AWS Lambda + API Gateway)**  
  - Funciones escritas en Go y desplegadas en AWS Lambda.  
  - `createReservation`: recibe petición POST, valida capacidad (máximo 7 personas/hora) y horario (08:00–22:00 en intervalos de hora), y crea o rechaza la reserva.  
  - `listActiveReservations`: responde a GET con todas las reservas cuya fecha de inicio sea igual o posterior a la fecha actual.  
  - `listReservationsByDateRange`: recibe POST con `startDate` y `endDate` para filtrar el historial de reservas.

- **Persistencia (DynamoDB)**  
  - Tabla `Reservations` con clave primaria `reservationId`.  
  - Atributos: `email`, `name`, `userId`, `labId`, `startTime`.  
  - Índice secundario global sobre `startTime` para búsquedas por fecha.

**Colaboración:** desarrollado junto a [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/).

## Funcionalidades clave

- Registro de reservas con validación automática de reglas de negocio.  
- Visualización de reservas activas (fechas no expiradas).  
- Filtrado de historial de reservas por rango de fechas.  
- Cumplimiento de capacidad (7 personas por hora) y franjas horarias (08:00–22:00).

## Tecnologías utilizadas

- **Serverless & API**  
  - [Go](https://golang.org/)  
  - [AWS Lambda](https://aws.amazon.com/lambda/)  
  - [AWS API Gateway](https://aws.amazon.com/api-gateway/)  
  - [AWS DynamoDB](https://aws.amazon.com/dynamodb/)

- **Frontend**  
  - [Astro](https://astro.build/)  
  - [ReactJS](https://reactjs.org/)  
  - Netlify

## Desarrollo de la práctica

1. **Interfaz estática**  
   - Construida con Astro y ReactJS, publicada en Netlify.  
   - Formularios y componentes interactivos que consumen las funciones Lambda.

2. **Funciones serverless**  
   - Escritas en Go y desplegadas en AWS Lambda + API Gateway, gestionan la creación, validación y consulta de reservas.

3. **Base de datos NoSQL**  
   - DynamoDB almacena reservas activas y archivo histórico, con índices para consultas eficientes.

## Despliegue

- **Frontend:** se publica automáticamente en Netlify tras cada push a la rama `main`.  
- **Backend:** funciones Lambda y tabla DynamoDB configuradas en AWS.

### Demo de la aplicación

<iframe width='100%' height="500" src="https://www.youtube.com/embed/Jls5cCJCpKU?si=m-u79OLDjmLK3AZw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Repositorio de GitHub

::github{repo="nightmareVCO/advanced-web"}
