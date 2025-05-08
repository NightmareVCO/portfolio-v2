---
title: ChronoGuard
published: 2025-03-03
description: 'Aplicación web para gestionar eventos en la agenda de gerentes.'
image: "./cover.png"
tags: [SpringBoot, Vaadin, Docker, Resend, PostgreSQL]
category: "Practica"
draft: false
---

# ChronoGuard – Gestión de Agenda de Gerentes

ChronoGuard es una aplicación web empresarial para gestionar eventos en la agenda de gerentes, con interfaz RIA (SPA) en Vaadin y lógica de negocio en Spring Boot. Permite crear, visualizar y actualizar eventos en un calendario interactivo, y envía notificaciones transaccionales por correo a los gerentes usando Resend, según la configuración de cada evento.

## Detalles de la aplicación

- **Frontend (Vaadin Flow)**  
  - SPA construida con Vaadin Flow: grids, formularios vinculados con Binder/DataProvider y el componente Full Calendar Flow para un calendario interactivo.  
  - Arrastrar y soltar eventos para re-programar fechas con actualizaciones en tiempo real.

- **Backend (Spring Boot)**  
  - Servicios REST con Spring MVC y lógica de negocio en Spring Boot.  
  - Autenticación y autorización con Spring Security; roles **ADMIN** y **USUARIO** para proteger vistas y operaciones críticas.  
  - Notificaciones transaccionales por correo: integración con [Resend](https://resend.com/) para envío de correos HTML mediante plantillas.  
  - Tareas programadas (`@Scheduled`) que disparan correos antes de la hora configurada en cada evento.

- **Persistencia**  
  - Base de datos relacional  (PostgreSQL) para almacenar usuarios, gerentes y eventos.  

- **Contenedores y orquestación**  
  - Docker Compose orquesta servicios: aplicación Spring Boot, base de datos.
  - Variables de entorno parametrizables (puertos, credenciales de Resend, configuración de base de datos, etc.).

**Colaboración:** desarrollado junto a [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/).

## Funcionalidades clave

- **Control de acceso** con roles **ADMIN** (gestión completa de usuarios y eventos) y **USUARIO** (creación, edición y consulta de eventos).  
- **CRUD de gerentes y usuarios** con paginación, validaciones y soporte multilenguaje.  
- **Gestión de eventos**: creación, edición, eliminación y reubicación mediante drag-&-drop en el calendario.  
- **Notificaciones programadas**: envío automático de correos antes de cada evento usando Resend.  
- **SPA interactiva** sin recargas de página, con validaciones y feedback en tiempo real.

## Tecnologías utilizadas

- **Frameworks:** Spring Boot, Vaadin Flow  
- **Componentes Vaadin:** Grid, Binder, DataProvider, Full Calendar Flow  
- **Seguridad:** Spring Security, JWT  
- **Correo transaccional:** Resend  
- **Scheduling:** Spring Scheduling (`@Scheduled`)  
- **Persistencia:** H2 / MySQL / PostgreSQL; Redis (opcional)  
- **Contenedores:** Docker, Docker Compose  

## Desarrollo del proyecto

El desarrollo de ChronoGuard se organizó en varias fases, cada una implementada y validada con éxito:

- **Inicialización y configuración base**  
  Se generó el proyecto Spring Boot con los módulos Web, Security y Scheduling, y se integró Vaadin Flow a través de Maven/Gradle para el frontend.

- **Seguridad y roles**  
  Se configuró Spring Security para manejar formularios de login y autorización por roles **ADMIN** y **USUARIO**, asegurando acceso selectivo a vistas y operaciones.

- **Modelado de datos y CRUD**  
  Se definieron las entidades JPA (`Gerente`, `Usuario`, `Evento`) y sus repositorios. En el frontend, Vaadin Grid y Binder/DataProvider permitieron construir interfaces para crear, editar y listar gerentes y usuarios.

- **Calendario interactivo**  
  Se incorporó el componente Full Calendar Flow para visualizar y manipular eventos. El drag-and-drop quedó habilitado y persiste cambios automáticamente en el backend.

- **Notificaciones con Resend**  
  Se integró la API de Resend en el servicio de correo de Spring Boot, desarrollando plantillas HTML y programando tareas con `@Scheduled` para enviar avisos antes de cada evento.

- **Contenerización y despliegue**  
  Se creó un `Dockerfile` multi-stage para la aplicación y un `docker-compose.yml` que levanta la app, la base de datos y Redis (opcional), facilitando el despliegue reproducible en cualquier entorno.

### Demo de la aplicación

<iframe width='100%' height="500" src="https://www.youtube.com/embed/T50lRBqSpDY?si=CpVmZmk80JWUI3-n" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Repositorio de GitHub

::github{repo="nightmareVCO/advanced-web"}
