---
title: Isolashes V2
published: 2024-12-29
description: 'Landing Web App para la empresa Isolashes. Mostrando los servicios que ofrece la empresa, sistemas de citas y tienda virtual.'
image: ''
tags: [Astro, React, TailwindCSS, WixStudio, Golang]
category: 'Proyecto'
draft: true
---

# Isolashes V2

[Isolashes](https://isolashes.com/) es una Landing Web App para la empresa Isolashes, salón y academia de pestañas. Esta aplicación web cuenta con dos versiones, una en NextJS y otra en Astro que es la versión en linea, ver [aquí](https://isolashes.com).

Está es la segunda versión de la aplicación, la cual fue segmentada en micro-servicios y las paginas de landing y tienda virtual se descaplarón en dos aplicaciones, una para la Landing y otra para la Tienda Virtual, la cual se mantuvo en NextJS pero se le realizaron cambios a la interfaz gráfica y al servidor.

Como servidor principal se utilizó WixStudio[https://manage.wix.com/studio], el cual se encarga de manejar los productos, los clientes, las citas y las ordenes de compra. Para el booking se utilizó [SetMore](https://www.setmore.com/), el cual se encarga de manejar las citas de los clientes y mediante Google Calendar se sincroniza (usando webhooks) con el servidor encargado de las citas y las manda a WixStudio.

Al momento de realizar pagos, se creo una pequeña pasarela de pago utilizando Go y React, la cual se encarga de manejar los pagos de los productos de la tienda virtual, utilizando [CardNet](https://www.cardnet.com.do).