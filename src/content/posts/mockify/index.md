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

Mockify es una aplicación cliente-servidor para crear y gestionar mocks de APIs REST, ideal para agilizar pruebas y desarrollo colaborativo. El servidor, construido en Spring Boot, expone endpoints configurables y balanceados, mientras que el cliente en Next.js y Tailwind CSS ofrece una interfaz limpia para administrar proyectos, mocks y usuarios.

## Detalles de la aplicación

- **Servidor (Spring Boot)**  
  - **Seguridad y JWT**: autenticación y autorización con Spring Security y tokens JWT; solo ADMIN puede eliminar proyectos/mocks y gestionar usuarios .
  - **Sesiones distribuidas y caché**: Redis actúa como almacén de sesiones (Spring Session) y base de datos NoSQL para metadatos de mocks .  
  - **Balanceo de carga**: HAProxy configurado en modo round-robin con health checks y terminación SSL para garantizar alta disponibilidad ractica Balanceador de Carga,  Sesiones Distribuidas y Contenedores - Clone Mocky.  
  - **Internacionalización (i18n)**: toda la aplicación está internacionalizada, permitiendo su vista en inglés o español.

- **Cliente (Next.js + Tailwind CSS)**  
  - Interfaz responsiva para CRUD de proyectos, mocks y usuarios.  
  - Formularios avanzados que definen ruta, método HTTP, headers, status code, content-type, cuerpo, expiración, delay y protección JWT.  
  - Protege rutas sensibles integrando JWT en cookies HTTP-only.

- **Proxy inverso**  
  - Configuración de Apache HTTPD incluida en el repositorio, con redirección HTTP→HTTPS y certificados Let’s Encrypt.

## Funcionalidades clave

- **Gestión de Proyectos y Mocks**  
  - Crear y editar proyectos; asociar múltiples mocks.  
  - Mocks personalizables: respuestas en JSON, XML o HTML; headers, status code, latencia (delay); expiración configurable.  
  - Protección opcional de mocks mediante JWT con vigencia igual al periodo de expiración.

- **Gestión de Usuarios y Roles**  
  - Registro y login con JWT; roles ADMIN/MEMBER.  
  - ADMIN crea/elimina usuarios, asigna roles y elimina proyectos/mocks; MEMBER solo crea/edita.

- **Alta disponibilidad y escalabilidad**  
  - Réplicas de servidor tras HAProxy.  
  - Orquestación con Docker Compose: instancias de Spring Boot, Redis, HAProxy y cliente Next.js.  
  - Variables de entorno para parametrizar puertos, credenciales y conexiones.

## Tecnologías utilizadas

- **Backend**  
  - Java & Spring Boot (MVC, REST, Security)  
  - Redis (sesión distribuida y caché)  
  - HAProxy (load balancer SSL/TLS)  
  - JWT (JSON Web Tokens)

- **Frontend**  
  - Next.js (React SSR/SSG)  
  - Tailwind CSS  

- **Infraestructura**  
  - Docker, Docker Compose  
  - Apache (reverse proxy)  
  - Let’s Encrypt (certificados SSL)

## Desarrollo del proyecto

La implementación de Mockify se llevó a cabo en varias etapas, todas completadas con éxito:

- **Spring Boot y REST API**  
  Se integró Spring Security con JWT, se definieron los modelos de dominio (`User`, `Role`, `Project`, `Mock`) y se implementaron los endpoints REST con validaciones, paginación e internacionalización.

- **Sesiones distribuidas y caché**  
  Redis se configuró como almacén de sesiones (Spring Session) y como base de datos NoSQL para el caché de JWT.

- **Balanceo de carga**  
  HAProxy se desplegó en modo round-robin, con health checks activos y terminación SSL, garantizando alta disponibilidad del servicio.

- **Cliente en Next.js**  
  Se desarrollaron los componentes React para formularios de creación y edición de proyectos/mocks, listados dinámicos y protección de rutas utilizando JWT en cookies HTTP-only.

- **Contenerización y orquestación**  
  Se creó un `Dockerfile` multi-stage para servidor y cliente, y un `docker-compose.yml` que orquesta Spring Boot, Redis, HAProxy y Next.js en contenedores.

- **Despliegue en producción**  
  El stack completo se desplegó con Docker Compose en un servidor Linux, incluyendo la configuración de certificados Let’s Encrypt para HTTPS.

La aplicación fue desarrollada en conjunto con [Steven Mateo](https://www.linkedin.com/in/steven-manuel-mateo-ramos-6626152b2/)

## Demo de la aplicación

<iframe width="100%" height="500" src="https://www.youtube.com/embed/4V_lEfckXC4?si=eabLpfq8wfBbX4Lg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Repositorio de GitHub

::github{repo="nightmareVCO/mockify"}
