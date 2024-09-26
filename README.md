# Comparador de Vuelos Baratos

## 1. Idea de la Aplicación

**Descripción**:  
La aplicación será una página web que permitirá buscar y comparar vuelos baratos en tiempo real desde diversas fuentes online. Utilizará APIs de servicios de vuelos, como Skyscanner API y Amadeus API, para recopilar información y mostrar las mejores ofertas disponibles de manera personalizada para el usuario.

**Propósito**:  
Facilitar la búsqueda de vuelos económicos al permitir que los usuarios comparen precios en tiempo real sin necesidad de visitar múltiples sitios web. La web ofrece filtros avanzados, notificaciones de ofertas y una interfaz intuitiva.  

## 2. Audiencia Objetivo

**Público**:  
El público objetivo incluye viajeros frecuentes, turistas, profesionales que viajan por trabajo, y cualquier persona que desee encontrar vuelos económicos de manera eficiente.  

**Relevancia**:  
Este tipo de web es ideal para quienes buscan ahorrar dinero en sus desplazamientos aéreos, ya que elimina la necesidad de realizar comparaciones manuales entre diferentes sitios web de vuelos.  

## 3. Análisis de Mercado

**Investigación**:  
Existen competidores fuertes como Skyscanner, Kayak y Google Flights, que ya ofrecen comparaciones de vuelos. Sin embargo, nuestra web se diferenciará mediante funcionalidades más personalizadas, adaptadas a las necesidades individuales de cada usuario.  

**Oportunidad de Diferenciación**:

- **Mayor personalización**: La web ofrecerá alertas personalizadas para vuelos o rutas específicas.
- **Filtros avanzados**: Los usuarios podrán filtrar resultados por aerolíneas de bajo coste, escalas y descuentos exclusivos.
- **Compartir ofertas**: Integración con redes sociales y apps de mensajería para compartir las mejores ofertas de vuelo fácilmente.

## 4. Funcionalidades Clave

- **Comparador de vuelos en tiempo real**: Capacidad de buscar vuelos desde diversas fuentes en tiempo real, mostrando las mejores ofertas.
- **Filtros de búsqueda avanzados**: Permitir a los usuarios filtrar por precio, aerolínea, horario de vuelo, escalas y duración del viaje.
- **Alertas de precios**: Los usuarios recibirán notificaciones por correo electrónico o SMS cuando haya una oferta que coincida con sus criterios de búsqueda.
  -**Mapa interactivo**: Se visualizarán rutas y aeropuertos en un mapa interactivo para mejorar la experiencia del usuario.
- **Ofertas de última hora**: Sección dedicada a vuelos con ofertas especiales que se encuentran a pocos días de la fecha de salida, ayudando a los usuarios a aprovechar descuentos de última hora.
- **Integración de pagos**: Facilitar la compra de vuelos directamente desde la plataforma mediante la integración con pasarelas de pago como PayPal o tarjetas de crédito, ofreciendo un proceso seguro y rápido.
- **Historial de precios**: Los usuarios podrán visualizar la evolución del precio de los vuelos a lo largo del tiempo, permitiéndoles identificar el mejor momento para comprar.
- **Comentarios y reseñas de vuelos**: Incluir reseñas de otros usuarios sobre la calidad de las aerolíneas, el servicio y las rutas, ayudando a los usuarios a tomar decisiones informadas.
- **Conectar con redes sociales**: Integración con redes sociales y apps de mensajería para compartir las mejores ofertas de vuelo fácilmente.

## 5. Modelos de Ejecución

- **Introducción técnica**  
En el cliente, la ejecución del código es gestionada por el navegador del usuario, lo que permite actualizaciones inmediatas de la interfaz (UI) sin necesidad de recargar la página. Esto se logra mediante tecnologías como React y JavaScript, que gestionan el DOM de manera eficiente.  
En el servidor, Node.js se utiliza para realizar las llamadas a las APIs de terceros, procesar la lógica de negocio y enviar las respuestas formateadas al cliente. El entorno asíncrono de Node.js permite manejar múltiples solicitudes simultáneamente, optimizando el rendimiento.  

### Ejemplos de ejecución:  

- **Cliente (Frontend)**: El cliente utiliza JavaScript y TypeScript para gestionar las interacciones del usuario en tiempo real, como los filtros y la actualización de resultados sin recargar la página. Se utilizarán frameworks como React para mejorar la experiencia de usuario y garantizar una interfaz reactiva.  

    - **Ejemplo**:  
    Los filtros de búsqueda se ejecutan en el cliente utilizando React. Cuando el usuario ajusta un filtro, el estado de la aplicación se actualiza instantáneamente y muestra resultados de vuelos sin necesidad de hacer una nueva solicitud al servidor.  

    - **Ejemplo de ejecución**:
``` javascript  
function handleFlightSearch(filters) {
  fetch('/api/flights', {
  method: 'POST',
  body: JSON.stringify(filters),
  headers: { 'Content-Type': 'application/json' },
  })
  .then(response => response.json())
  .then(data => updateFlightResults(data));
  }
```  

- **Servidor (Backend)**: La lógica de negocio y las llamadas a las APIs de vuelos se gestionan en el servidor mediante Node.js y Express. Cuando el usuario busca vuelos para una fecha específica, el servidor utiliza Node.js para enviar solicitudes a las APIs de Skyscanner y Amadeus, combinando los resultados antes de enviarlos al cliente.  

    - **Ejemplo**:  
    Cuando el usuario busca vuelos para una fecha específica, el servidor utiliza Node.js para enviar solicitudes a las APIs de Skyscanner y Amadeus, combinando los resultados antes de enviarlos al cliente.

    - **Ejemplo de ejecución**:  
```javascript
app.post('/api/flights', (req, res) => {
  const filters = req.body;
  // Lógica para llamar a las APIs de Skyscanner y Amadeus
  fetchFlightsFromAPIs(filters).then(flightData => res.json(flightData));
  });
```  

## 6. Lenguajes de Programación Web

- **Frontend (Cliente)**:  
  **JavaScript**: Es compatible con todos los navegadores modernos y permite la actualización dinámica de la página.  
  **TypeScript**: Una evolución de JavaScript que agrega tipado estático, lo cual es esencial cuando se trabaja con datos provenientes de múltiples fuentes, como APIs de vuelos. TypeScript facilita la identificación de errores durante el desarrollo, mejorando la mantenibilidad y la escalabilidad del proyecto.

  - **Ventajas**:   
      JavaScript es flexible y ampliamente soportado, mientras que TypeScript reduce errores comunes durante el desarrollo al ofrecer tipado estático.  
  - **Desventajas**:  
      TypeScript tiene una curva de aprendizaje adicional, pero a largo plazo facilita el mantenimiento del código.  

- **Backend (Servidor)**:  
  **Node.js**: Es ideal para manejar múltiples solicitudes asíncronas de las APIs de vuelos. Al ser un entorno basado en JavaScript, permite compartir lógica de negocio entre cliente y servidor.  

  - **Ventajas**:  
      Manejo eficiente de múltiples solicitudes concurrentes y excelente rendimiento en tiempo real.  
  - **Desventajas**:  
      Para operaciones pesadas (como procesamiento de grandes datos), Node.js podría no ser la opción más eficiente en comparación con otros lenguajes como Java o Python.  

## 7. Tecnologías a Utilizar

- **Frontend**:  
    - **HTML y CSS** para la estructura y el estilo de la página.  
    - **JavaScript y TypeScript** para la lógica del cliente.  
    - **React**: Framework para crear una interfaz de usuario interactiva y escalable.  

- **Backend**: 
    - Node.js con Express, y uso de

  - **APIs de vuelos**:
    - [Skyscanner API](https://developers.skyscanner.net): Proporciona información sobre vuelos en tiempo real.
    - [Amadeus API](https://developers.amadeus.com): Alternativa robusta para obtener datos sobre vuelos.

- **Base de Datos**:  
No necesariamente requerida si los datos son obtenidos en tiempo real de las APIs, pero se puede utilizar MongoDB para almacenar preferencias de usuarios y alertas de precios.

**Justificación**:  
Node.js maneja eficazmente conexiones asíncronas a múltiples APIs de vuelos, lo cual es fundamental para una aplicación de búsqueda de vuelos en tiempo real. React mejora la interactividad de la interfaz, y TypeScript añade seguridad al código.

## 8. Integración de Lenguajes de Marcas con Lenguajes de Programación

**Descripción**:  
La integración de JSX en React permite que el HTML se mezcle con la lógica de JavaScript, lo que facilita la actualización de la interfaz de usuario de manera eficiente. Esta integración mejora tanto la experiencia del usuario como el mantenimiento del código, ya que el DOM se actualiza automáticamente en función de los cambios en los datos.

**Ejemplo práctico**:
- Cuando el servidor envía los resultados de vuelos al cliente, React los procesa y actualiza dinámicamente el DOM, mostrando los vuelos al usuario de forma rápida y eficiente.

``` javascript
function FlightResults({ flights }) {
  return (
    <div>
      {flights.map(flight => (
        <FlightCard key={flight.id} flight={flight} />
      ))}
    </div>
  );
```

## 9. Evaluación de Herramientas de Programación para Clientes Web

**Herramientas seleccionadas**:
- **Visual Studio Code**: Es el editor de código recomendado por su flexibilidad y excelente soporte para JavaScript y TypeScript, lo que facilita el desarrollo y depuración del proyecto.
- **React (opcional)**: Permite crear interfaces de usuario interactivas y escalables, lo cual es crucial para manejar los datos dinámicos de los vuelos y filtrar resultados en tiempo real.

**Justificación**:  
React se destaca por su simplicidad y flexibilidad en el manejo de interfaces dinámicas, mientras que Angular es más adecuado para aplicaciones más grandes y estructuradas. React fue seleccionado por su capacidad para manejar la interfaz de usuario con actualizaciones en tiempo real.

## 10. Compatibilidad en Navegadores
Los navegadores modernos como Chrome, Firefox, y Edge utilizan motores como V8 en Chrome para ejecutar JavaScript de manera eficiente. Esto asegura que las operaciones asíncronas (como las llamadas a las APIs de vuelos) no bloqueen la interacción del usuario con la página.  

**Análisis**:  
La mayoría de los navegadores modernos soportan las tecnologías empleadas en este proyecto, pero se deben considerar posibles diferencias en la implementación de algunas características.  

**Problemas comunes**:  
Podrían surgir problemas relacionados con el manejo de algunas APIs, ya que no todos los navegadores pueden soportar algunas de las características más recientes.

**Soluciones**:  
Se utilizarán bibliotecas de compatibilidad (como Polyfills) para resolver diferencias entre navegadores y garantizar que la aplicación funcione correctamente en todos ellos.

## Referencias

**APIs**:
- [**Skyscanner API**](https://developers.skyscanner.net) - Utilizada para obtener información en tiempo real sobre vuelos.
- [**Amadeus API**](https://developers.amadeus.com) - Alternativa robusta para obtener datos sobre vuelos y ofertas de viaje.
- [**IATA API**](https://developers.iata.org) - Ofrece acceso a una gran cantidad de datos relacionados con vuelos, aeropuertos y aerolíneas.

**Recursos de Aprendizaje**:
- [**"Introduction to Node.js with Express"**](https://nodejs.org/en/docs/guides/getting-started-guide/) - Guía práctica de introducción a Node.js y Express.
- [**"Understanding React and JSX"**](https://reactjs.org/docs/introducing-jsx.html) - Documentación oficial de React sobre el uso de JSX en aplicaciones web.
- [**"TypeScript Handbook"**](https://www.typescriptlang.org/docs/handbook/intro.html) - Manual oficial de TypeScript para el aprendizaje de su tipado estático.
- [**"MongoDB Atlas Documentation"**](https://www.mongodb.com/docs/atlas/) - Documentación para el uso de bases de datos NoSQL en la nube con MongoDB Atlas.
- [**"REST API Design Guide"**](https://restfulapi.net/) - Guía sobre mejores prácticas para diseñar e implementar APIs RESTful.

**Otros recursos**:
- Flight Pricing and Data Analysis" - Artículo sobre cómo las API recopilan y procesan información de precios de vuelos en tiempo real. Disponible en Skyscanner Blog.
- "Trends in Travel Technology" - Un informe sobre las últimas tendencias en la industria tecnológica del viaje, destacando el uso de API y aplicaciones móviles. Disponible en Amadeus Travel Blog.
