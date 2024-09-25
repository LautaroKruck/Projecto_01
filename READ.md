# Comparador de Vuelos Baratos

## Descripción

La aplicación es una página web que permite a los usuarios buscar vuelos baratos en tiempo real. Se conecta a diversas fuentes online para comparar precios de vuelos y ofrecer las mejores ofertas disponibles al usuario. El objetivo es facilitar la búsqueda de vuelos económicos sin tener que visitar múltiples sitios web.

## Audiencia Objetivo

- **Público**: 
Personas que desean encontrar vuelos económicos, incluyendo viajeros frecuentes, turistas, y cualquier usuario que busque ahorrar dinero en sus desplazamientos aéreos.

- **Relevancia**: 
Este sitio web es particularmente útil para quienes buscan ofertas rápidas y eficientes sin necesidad de realizar comparaciones manuales en múltiples sitios web.

## Funcionalidades Clave

- **Comparador de vuelos**: Buscar vuelos en tiempo real desde varias fuentes online.
- **Filtros de búsqueda**: Posibilidad de filtrar por aerolíneas, precios, horarios y escalas.
- **Alertas de precios**: Notificaciones por email o SMS cuando haya una oferta que coincida con los criterios del usuario.
- **Integración con mapas**: Mostrar rutas y aeropuertos en un mapa interactivo.

## Análisis de Mercado

Existen competidores como Skyscanner, Kayak y Google Flights que ofrecen comparaciones de vuelos entre aerolíneas y agencias. La oportunidad de diferenciación se encuentra en:
- Mayor personalización en las búsquedas (alertas para vuelos específicos o rutas preferidas).
- Filtros detallados para aerolíneas de bajo coste y descuentos especiales.
- Integración con redes sociales o apps de mensajería para compartir ofertas.

## Tecnologías Utilizadas

- **Frontend**: HTML, CSS, JavaScript (o TypeScript para mayor seguridad).
- **Backend**: Node.js con Express, y uso de APIs de servicios de vuelos como [Skyscanner API](https://developers.skyscanner.net) o [Amadeus API](https://developers.amadeus.com).
- **Base de Datos**: MongoDB (opcional) para almacenar preferencias de usuarios y alertas de precios.

## Modelos de Ejecución

- **Cliente**: JavaScript permite que el usuario interactúe con los filtros de búsqueda en tiempo real sin necesidad de recargar la página.
- **Servidor**: Node.js maneja la lógica de búsqueda y las conexiones con las APIs de las plataformas de vuelos.
