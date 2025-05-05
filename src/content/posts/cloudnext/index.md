---
title: Cloud Next
published: 2024-10-27
description: "Aplicación web para subir archivos a la nube."
image: "./cover.png"
tags: [NextJS, React, TailwindCSS, Convex, Clerk]
category: "Proyecto"
draft: false
---

# Cloud Next

[Cloud Next](https://cloudnext-app.tech/) es una aplicación web de almacenamiento y gestión de archivos en la nube, desarrollada con Next.js y potenciada por Convex como BaaS en tiempo real, junto a Clerk para la autenticación. Gracias a su arquitectura serverless y real-time, ofrece una experiencia fluida tanto en la interfaz de usuario como en la sincronización de datos.

## Arquitectura y flujo de datos

- **Frontend en Next.js**  
  - Construido con el App Router de Next.js (v13+), aprovechando Server Components y Client Components para equilibrar rendimiento y reactividad.  
  - **Server Actions** nativas de Next.js que ejecutan en el servidor la lógica de subida a S3, generación de Signed URLs y actualización de metadatos en Convex, sin necesidad de rutas API explícitas.  
  - Páginas estáticas e Incremental Static Regeneration (ISR) para optimizar TTFB y SEO.  
  - Tailwind CSS para estilos utilitarios y diseño responsivo.

- **BaaS en Convex**  
  - Base de datos en tiempo real con suscripciones automáticas: al crear, actualizar o eliminar metadatos de un archivo, todos los clientes conectados reciben la actualización al instante.  
  - Convex Functions (`uploadMetadata`, `deleteMetadata`, `toggleFavorite`, `listFiles`) encapsulan la lógica de negocio y las validaciones de seguridad.  
  - Caché cliente integrado y sincronización offline/online sin configuración adicional.

- **Autenticación y autorización con Clerk**  
  - Clerk gestiona flujos completos: registro con credenciales o Single Sign-On (Google), verificación de correo y protección de rutas en Next.js.  
  - Soporta roles de usuario (administrador, editor) y organizaciones, permitiendo controles de acceso granulares.

- **Almacenamiento de archivos en AWS S3**  
  - Los archivos binarios se guardan en un bucket de S3; las Server Actions de Next.js generan Signed URLs para subida y descarga seguras.  
  - La metadata (nombre, URL firmado, tamaño, propietario, favorito) se mantiene y sincroniza en Convex.

## Funcionalidades principales

- Subida de archivos con barra de progreso y validación de tamaño/formato.  
- Listado en tiempo real de archivos (propios, organizacionales o públicos).  
- Descarga y eliminación de archivos mediante Signed URLs de S3.  
- Marcar o desmarcar archivos como favoritos.  
- Sincronización instantánea entre todos los usuarios conectados.  
- Gestión de acceso y permisos a través de roles y organizaciones en Clerk.

## Tecnologías utilizadas

- **Framework**: [Next.js](https://nextjs.org/)  
- **UI & Estilos**: React, Tailwind CSS  
- **BaaS & Tiempo real**: [Convex](https://docs.convex.dev/home)  
- **Autenticación**: [Clerk](https://clerk.dev/)  
- **Almacenamiento de archivos**: AWS S3  
- **Hosting**: Vercel (frontend)  

## Desarrollo del proyecto

1. **Inicialización**  
   - Configurar Next.js con TypeScript, App Router y variables de entorno para Convex, Clerk y S3.  
   - Integrar Tailwind CSS para estilos.

2. **Convex**  
   - Definir esquemas de datos y escribir Functions: `uploadMetadata`, `deleteMetadata`, `toggleFavorite`, `listFiles`.  
   - Configurar reglas de acceso basadas en roles y organizaciones.

3. **Clerk**  
   - Instalar Clerk SDK en Next.js, proteger rutas y montar componentes de UI para login/registro.  
   - Configurar roles de usuario y asignación a organizaciones.

4. **Server Actions en Next.js**  
   - Implementar `uploadFile`, `deleteFile`, `toggleFavorite` y `listFiles` como Server Actions dentro de componentes de servidor.  
   - Cada acción:  
     - Solicita Signed URL a S3 y realiza la operación en el bucket.  
     - Actualiza o consulta la metadata en Convex.

5. **Interfaz y sincronización**  
   - Usar hooks de Convex (`useQuery`, `useMutation`) en componentes React para obtener datos en tiempo real.  
   - Manejar estados de carga, errores y actualizaciones en vivo.

6. **Despliegue**  
   - Publicar el frontend en Vercel con dominio personalizado.  
   - Configurar bucket de S3 con políticas CORS y ciclo de vida.

## Repositorio de GitHub

::github{repo="nightmareVCO/next-file-cloud"}
