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

[Cloud Next](https://cloudnext-app.tech/) es una aplicación web para subir archivos a la nube. Se utilizó [Convex](https://docs.convex.dev/home) como BaaS, [Clerk](https://www.convex.dev/) para la autenticación y [NextJS](https://nextjs.org/) como framework de React.

Esta aplicación permite a los usuarios subir archivos a la nube, ver los archivos subidos, descargar los archivos subidos y eliminar los archivos subidos y marcar archivos como favoritos. Los usuarios pueden registrarse utilizando su cuenta de google o con credenciales creadas y Clerk se encargar de enviar correos de validación.

Los usuarios autenticados tienen acceso a todas las funcionalidades. Los usuarios no autenticados pueden ver la página de inicio, la página de registro y la página de inicio de sesión, esto se controla con Clerk. Utilizando clerk se puede crear roles de usuario, como administrador, editor, etc. Además, se pueden crear organizaciones y asignar usuarios a organizaciones con distintos roles y permisos para los mismos.

Convex permite que la aplicación funcione en tiempo real, es decir, si un usuario sube un archivo, los demás usuarios verán el archivo subido en tiempo real. Convex otorga una gran escalabilidad a la aplicación, ya que se puede escalar horizontalmente sin problemas.

## Listado de tecnologías utilizadas

- [NextJS](https://nextjs.org/)
- [React](https://reactjs.org/)
- [TailwindCSS](https://tailwindcss.com)
- [Convex](https://docs.convex.dev/home)
- [Clerk](https://www.convex.dev/)
- [Google Cloud](https://cloud.google.com/)

## Repositorio de GitHub

::github{repo="nightmareVCO/next-file-cloud"}
