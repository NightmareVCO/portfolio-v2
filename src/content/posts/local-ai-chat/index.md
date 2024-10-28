---
title: Local Multi Model AI Chat
published: 2024-07-05
description: 'Chatbot local que utiliza múltiples modelos de inteligencia artificial a elección del usuario.'
image: './cover.png'
tags: [NextJS, React, TailwindCSS, WebGPU]
category: 'Proyecto'
draft: false
---

# Local Multi Model AI Chat

[Local Multi Model AI Chat](https://local-ai-chat-bot-vc.vercel.app/) es un chatbot local que utiliza múltiples modelos de inteligencia artificial a elección del usuario. Se utilizó [NextJS](https://nextjs.org/) como framework de React, [TailwindCSS](https://tailwindcss.com) como framework de diseño y [WebGPU](https://gpuweb.github.io/gpuweb/) para acelerar los cálculos de los modelos de inteligencia artificial.

Es importante mencionar que este chatbot no utiliza una API para realizar las predicciones, sino que utiliza los modelos de inteligencia artificial de manera local, lo que permite al usuario seleccionar el modelo que desea utilizar pero también requiere de un mayor poder de procesamiento.

Este chatbot permite al usuario seleccionar el modelo de inteligencia artificial que desea utilizar, entre los modelos disponibles se encuentran:

- [Llama](https://llama.meta.com/)
- [Phi](https://azure.microsoft.com/en-us/products/phi-3)
- [Qwen](https://github.com/QwenLM/Qwen)
- [Gemma](https://ai.google.dev/gemma)

### Mejoras de la aplicación

- Integrar historial de conversaciones
- Integrar reconocimiento de voz
- Integrar configuración de modelos con ajustes como: temperatura, top-k, top-p, etc.

### Repositorio de GitHub

::github{repo="nightmareVCO/local-ai-chat-bot"}
