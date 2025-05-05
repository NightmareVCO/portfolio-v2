---
title: BookHive
published: 2025-04-28
description: "BookHive es una plataforma moderna de catálogo de libros para búsqueda, compra y reseña de títulos, con microservicios en Spring Boot, frontend en Next.js."
image: "./cover.png"
tags: [SpringBoot, Microservices, NextJS, JasperReports, DataFaker, PayPal]
category: "Proyecto"
draft: false
---

# BookHive – Plataforma de Búsqueda, Compra y Reseña de Libros

BookHive es una solución diseñada bajo una arquitectura de microservicios para ofrecer un catálogo dinámico de libros, un sistema de compras simuladas y un módulo de reseñas, todo ello con alta disponibilidad, escalabilidad y trazabilidad distribuida. La aplicación permite a los usuarios buscar libros, añadirlos a un carrito de compras y dejar reseñas, todo ello con una interfaz moderna y responsiva.

## Arquitectura general

- **Microservicios independientes** con Spring Boot y Spring Cloud: cada servicio se despliega de forma autónoma y se comunica mediante APIs REST síncronas.  
- **Descubrimiento y configuración centralizada**: Spring Cloud Netflix Eureka para registro de instancias y Spring Cloud Config Server para gestión de propiedades.  
- **Gateway API**: Spring Cloud Gateway actúa como punto de entrada único, realizando enrutamiento dinámico, filtrado de peticiones y balanceo entre réplicas.  
- **Trazabilidad distribuida**: Zipkin integrado en cada servicio para rastrear flujos de solicitudes y facilitar el diagnóstico de cuellos de botella.

## Frontend

- **Next.js**  
  - App Router con Server & Client Components para equilibrar rendimiento y reactividad.  
  - SSG/ISR para catálogo y SEO, componentes cliente para interacciones dinámicas.  

- **Estado global con Zustand**  
  - Store global para el carrito de compras: añadir, eliminar y mantener ítems en memoria.  
  - Suscripción ligera que optimiza re-renderizados.

## Componentes principales

1. **Catálogo de Libros**  
   - Gestión de búsqueda por título, autor y género.  
   - Persistencia en MongoDB con datos de ejemplo generados por DataFaker.

2. **Carrito de Compras**  
   - CRUD de ítems y de pedidos.  
   - Base de datos relacional (PostgreSQL) para estado del carrito y pedidos.  

3. **Autenticación y autorización**  
   - Spring Security con JSON Web Tokens (JWT).  
   - Roles `ADMIN` y `CLIENTE` para control granular de acceso.  

4. **Reseñas de usuarios**  
   - Permite publicar, y consultar valoraciones de libros.  
   - Almacenamiento en base de datos SQL (PostgreSQL).

5. **Notificaciones y facturación**  
   - Servicio de correo transaccional que envía confirmaciones de registro y facturas en PDF.  
   - Generación de reportes con JasperReports e integración SMTP.

6. **Alta disponibilidad y escalabilidad**  
   - Cada microservicio se ejecuta en al menos dos instancias.
   - Orquestación con Docker Compose, definiendo réplicas, redes y volúmenes compartidos.
   - El Gateway supervisa la salud de las instancias y distribuye la carga de forma inteligente.

## Integraciones externas

- **DataFaker** para poblar el catálogo de libros con datos de prueba.  
- **PayPal** para pagos electrónicos.  
- **JasperReports** para generación automática de facturas en PDF.  
- **Zipkin** para seguimiento distribuido de transacciones entre servicios.

## Seguridad

- Comunicaciones cifradas (HTTPS) y validación de tokens JWT en cada llamada.  
- Políticas de CORS y filtrado en el API Gateway.  

## Contenerización y despliegue

- **Dockerfile** multi-stage en cada repositorio de servicio.  
- Archivo `docker-compose.yml` que levanta todos los servicios, bases de datos y herramientas auxiliares con réplicas configuradas.  
- Configuración de variables de entorno para entornos de desarrollo, staging y producción.

**Colaboración:** desarrollado junto a [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/)

## Demo de la aplicación

<iframe width='100%' height="500" src="https://www.youtube.com/embed/LznAX3MZkr0?si=hPa6_T0TQ_H8Sbbk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

**Repositorio principal:**  

::github{repo="nightmareVCO/BookHive"}
