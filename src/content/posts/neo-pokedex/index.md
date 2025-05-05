---
title: Neo Pokédex
published: 2024-12-03
description: 'Aplicación móvil creada en Flutter para ver información de los pokemones consumiendo la PokeAPI con GraphQL.'
image: './cover.png'
tags: [Flutter, GraphQL]
category: 'Proyecto'
draft: false
---

# Neo Pokédex

Neo Pokédex es una aplicación móvil cross-platform desarrollada en Flutter y Dart para explorar información detallada de los Pokémon consumiendo la PokeAPI mediante GraphQL Proyecto_Flutter.pdf](file-service://file-ER5LEwaVjCpnuAxdRkBnQr). Permite ver la lista de Pokémon, consultar detalles, buscar por nombre o número y marcar favoritos.

## Detalles de la aplicación

- **Interfaz de Usuario**  
  - Pantalla de listado con nombre, imagen y tipos de cada Pokémon.  
  - Barra de búsqueda por nombre o número.  
  - Pantalla de detalles que muestra nombre, tipo, estadísticas, habilidades, evoluciones y movimientos.  
  - Marcado de Pokémon como favoritos, almacenando localmente la lista personalizada. Proyecto_Flutter.pdf](file-service://file-ER5LEwaVjCpnuAxdRkBnQr)

- **Integración con GraphQL**  
  - Queries optimizadas para obtener la lista con paginación y los detalles específicos de un Pokémon.  
  - Consumo de la API GraphQL de PokeAPI para obtener datos en tiempo real. Proyecto_Flutter.pdf](file-service://file-ER5LEwaVjCpnuAxdRkBnQr)

- **Navegación y experiencia**  
  - Navegación fluida entre lista y detalles con animaciones y transiciones.  
  - Sistema de filtrado y ordenación por tipo, generación, habilidades, poder y estadísticas. Proyecto_Flutter.pdf](file-service://file-ER5LEwaVjCpnuAxdRkBnQr)

- **Otras funcionalidades**  
  - Compartir “tarjeta” de un Pokémon a través de redes sociales u otros medios.  
  - Persistencia local de favoritos usando Hive y shared_preferences.  
  - Personalización de la interfaz con elementos gráficos y animaciones avanzadas. Proyecto_Flutter.pdf](file-service://file-ER5LEwaVjCpnuAxdRkBnQr)  
  - Opcional: modo offline para favoritos, sección de trivia y mapa interactivo de regiones. Proyecto_Flutter.pdf](file-service://file-ER5LEwaVjCpnuAxdRkBnQr)

**Colaboración:** desarrollado junto a [Natasha López](https://github.com/Natashalopez05).

## Tecnologías utilizadas

- [Flutter](https://flutter.dev/) & [Dart](https://dart.dev/)  
- [GraphQL](https://graphql.org/) (paquete `graphql_flutter`)  
- [Hive](https://hivedb.dev/) & `shared_preferences`  
- Plugins: `flutter_animate`, `share_plus`, `cached_network_image`

## Desarrollo de la práctica

1. Configuración del cliente GraphQL y definición de consultas para lista y detalles.  
2. Implementación de la UI de listado con paginación, búsqueda, filtrado y ordenación.  
3. Pantalla de detalles con secciones para estadísticas, habilidades, evoluciones y movimientos.  
4. Gestión de favoritos con Hive para persistencia local y soporte offline.  
5. Animaciones y transiciones entre pantallas usando `Hero` y `AnimatedContainer`.  
6. Funcionalidad de compartir información de Pokémon con `share_plus`.

## Demo de la aplicación

<iframe width="100%" height="500" src="https://www.youtube.com/embed/8RB5UzN9IyA?si=q_yUKi6pXSJdggm9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Repositorio de GitHub

::github{repo="nightmareVCO/neo_pokedex"}