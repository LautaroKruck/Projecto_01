# Comparador de Vuelos Baratos

## 1. Idea de la Aplicación

**Descripción**:  
La aplicación será una página web que permitirá buscar y comparar vuelos baratos en tiempo real desde diversas fuentes online. Utilizará APIs de servicios de vuelos para recopilar información y mostrar las mejores ofertas disponibles de manera personalizada para el usuario.

**Propósito**:  
Facilitar la búsqueda de vuelos económicos al permitir que los usuarios comparen precios en tiempo real sin necesidad de visitar múltiples sitios web. La aplicación ofrece filtros avanzados, notificaciones de ofertas y una interfaz fácil de usar.

## 2. Audiencia Objetivo

**Público**:  
El público objetivo incluye viajeros frecuentes, turistas, profesionales que viajan por trabajo, y cualquier persona que desee encontrar vuelos económicos de manera eficiente.

**Relevancia**:  
Este tipo de web es ideal para quienes buscan ahorrar dinero en sus desplazamientos aéreos, ya que elimina la necesidad de realizar comparaciones manuales entre diferentes sitios web de vuelos.

## 3. Análisis de Mercado

**Investigación**:  
Existen competidores fuertes como Skyscanner, Kayak y Google Flights, que ya ofrecen comparaciones de vuelos. Sin embargo, hay espacio para diferenciarse a través de funcionalidades específicas y más personalizadas.

**Oportunidad de Diferenciación**:

- **Mayor personalización**: La aplicación ofrecerá alertas personalizadas para vuelos o rutas específicas.
- **Filtros avanzados**: Los usuarios podrán filtrar resultados por aerolíneas de bajo coste, escalas y descuentos exclusivos.
- **Compartir ofertas**: Integración con redes sociales y apps de mensajería para compartir las mejores ofertas de vuelo fácilmente.

## 4. Funcionalidades Clave

- **Comparador de vuelos en tiempo real**: Capacidad de buscar vuelos desde diversas fuentes en tiempo real, mostrando las mejores ofertas.
- **Filtros de búsqueda avanzados**: Permitir a los usuarios filtrar por precio, aerolínea, horario de vuelo, escalas y duración del viaje.
- **Alertas de precios**: Los usuarios recibirán notificaciones por correo electrónico o SMS cuando haya una oferta que coincida con sus criterios de búsqueda.
- **Mapa interactivo**: Se visualizarán rutas y aeropuertos en un mapa interactivo para mejorar la experiencia del usuario.

## 5. Modelos de Ejecución

- **Cliente (Frontend)**: El cliente utiliza JavaScript y TypeScript para gestionar las interacciones del usuario en tiempo real, como los filtros y la actualización de resultados sin recargar la página. Se utilizarán frameworks como React para mejorar la experiencia de usuario y garantizar una interfaz reactiva.

**Ejemplo**:
Los filtros de búsqueda se ejecutan en el cliente utilizando React. Cuando el usuario ajusta un filtro, el estado de la aplicación se actualiza instantáneamente y muestra resultados de vuelos sin necesidad de hacer una nueva solicitud al servidor.

- **Servidor (Backend)**: La lógica de negocio y las llamadas a las APIs de vuelos se gestionan en el servidor mediante Node.js y Express. El servidor procesa las solicitudes del cliente, se comunica con las APIs externas (como Skyscanner y Amadeus) y devuelve los datos formateados.

**Ejemplo**:
Cuando el usuario busca vuelos para una fecha específica, el servidor utiliza Node.js para enviar solicitudes a las APIs de Skyscanner y Amadeus, combinando los resultados antes de enviarlos al cliente.

### Ejemplos Concretos de ejecución:

- **Cliente**:
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
- **Servidor**:
```javascript
app.post('/api/flights', (req, res) => {
  const filters = req.body;
  // Lógica para llamar a las APIs de Skyscanner y Amadeus
  fetchFlightsFromAPIs(filters).then(flightData => res.json(flightData));
  });
```

## 6. Lenguajes de Programación Web

- **Frontend (Cliente)**:  
  JavaScript: Es ampliamente compatible con todos los navegadores y permite la actualización dinámica de la página.  
  TypeScript: Añade tipado estático, lo que mejora la robustez y mantenibilidad del código, especialmente útil cuando se manejan datos complejos como los obtenidos de múltiples APIs.

- **Ventajas**: JavaScript es flexible y ampliamente soportado, mientras que TypeScript reduce errores comunes durante el desarrollo al ofrecer tipado estático.
- **Desventajas**: TypeScript tiene una curva de aprendizaje adicional, pero a largo plazo facilita el mantenimiento del código.

    - **Backend (Servidor)**:  
      Node.js: Es ideal para manejar múltiples solicitudes asíncronas de las APIs de vuelos. Al ser un entorno basado en JavaScript, permite compartir lógica de negocio entre cliente y servidor.

- **Ventajas**: Manejo eficiente de múltiples solicitudes concurrentes y excelente rendimiento en tiempo real.
- **Desventajas**: Para operaciones pesadas (como procesamiento de grandes datos), Node.js podría no ser la opción más eficiente en comparación con otros lenguajes como Java o Python.

## 7. Tecnologías a Utilizar

- **Frontend**: HTML, CSS, JavaScript (React o TypeScript para mayor seguridady manteniimiento).

- **Backend**: Node.js con Express, y uso de

- **APIs de vuelos**:
- - [Skyscanner API](https://developers.skyscanner.net): Proporciona información sobre vuelos en tiempo real.
- - [Amadeus API](https://developers.amadeus.com): Alternativa robusta para obtener datos sobre vuelos.

- **Base de Datos**: No necesariamente requerida si los datos son obtenidos en tiempo real de las APIs, pero se puede utilizar MongoDB para almacenar preferencias de usuarios y alertas de precios.

**Justificación**:  
Node.js maneja eficazmente conexiones asíncronas a múltiples APIs de vuelos, lo cual es fundamental para una aplicación de búsqueda de vuelos en tiempo real. React mejora la interactividad de la interfaz de usuario, y TypeScript añade seguridad y robustez al código.

## 8. Integración de Lenguajes de Marcas con Lenguajes de Programación

**Descripción**:  
El HTML proporciona la estructura de la página web, mientras que JavaScript y TypeScript interactúan dinámicamente con el DOM para actualizar los resultados de la búsqueda sin recargar la página. Esta integración entre lenguajes permite a los usuarios ver resultados de vuelos en tiempo real.

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
React ofrece una interfaz reactiva que mejora la experiencia del usuario, mientras que Visual Studio Code proporciona herramientas robustas para un desarrollo ágil y eficiente.

## 10. Compatibilidad en Navegadores

**Análisis**:  
Los navegadores modernos (Chrome, Firefox, Edge) soportan JavaScript y las APIs que utilizaremos. Sin embargo, es importante considerar posibles diferencias en la implementación de características, especialmente para usuarios de navegadores más antiguos.

**Problemas comunes**:  
Podrían surgir problemas relacionados con el manejo de algunas APIs, ya que no todos los navegadores pueden soportar algunas de las características más recientes.

**Soluciones**:  
Se utilizarán bibliotecas de compatibilidad (como Polyfills) para resolver diferencias entre navegadores y garantizar que la aplicación funcione correctamente en todos ellos.

## Referencias

**APIs**:
- **Skyscanner API** - Utilizada para obtener información en tiempo real sobre vuelos.
- **Amadeus API** - Alternativa para obtener datos de vuelos.

**Recursos de aprendizaje**:
- **"Introduction to Node.js with Express"** - Obtenido de https://example.com/tutorial-nodejs
  Licencia Creative Commons Attribution 4.0.
