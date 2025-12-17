# Análisis de Peticiones y Respuestas HTTP con HTTP Header
--- 

## Parte 1: Instalación y configuración

### Instalación de la extensión
Se ha instalado la extension **HTTP Header** en el navegador **Brave**, la cual permite capturar y analizar el tráfico HTTP generado durante la navegación web.

![Captura extensión instalada](/ExtencionInstalada.png)

## Parte 2: Captura de peticiones HTTP
Para esta parte se ha activado la captura de tráfico HTTP mediante la extensión **HTTP Header**
y se ha navegado a tres URLs distintas del mismo dominio.

## URL A: https://librebits.info

### Petición HTTP capturada

![Captura URL A](/CapturaGET-200.png)

## URL B: https://librebits.info/404

### Petición HTTP capturada

![Captura URL B](/CapturaGET-404.png)

## URL C: https://docs.google.com/forms/u/0/d/e/1FAIpQLSezxy_6IX8cr0QFflO0ZODlYyrLoV8YGdUl7Dw55It-O03Tpw/formResponse

### Peticion HTTP capturada

![Captura URL C](/CapturaPOST.png)

## Análisis de los elementos capturados

**Host**: Indica el nombre del dominio al que se dirige la petición HTTP.
Es esencial cuando un servidor aloja varios sitios web en la misma dirección IP.
Permite al servidor saber qué página concreta debe servir al cliente.

**User-Agent**: Identifica el navegador, el sistema operativo y, en algunos casos, el dispositivo del cliente.
El servidor puede usar esta información para adaptar el contenido o aplicar compatibilidad.
También se utiliza para estadñisticas y detección de clientes.

**Accept**: Especifica los tipos de contenido que el cliente es capaz de recibir, como HTML, JSON o imágenes.
Permite al servidor seleccionar el formato más adecuado para responder.
Forma parte del mecanismo de negociación de contenido.

**Upgrade-Insecure-Requests**: Indica que el navegador prefiere recibir los recursos mediante conexiones seguras.
Se utiliza para solicitar al servidor que convierta peticiones HTTP en HTTPS cuando sea posible.
Mejora la seguridad evitando contenido no cifrado.

**Sec-CH-UA**: Proporciona información estructurada sobre el navegador del cliente.
Forma parte de las Client Hints, diseñadas para mejorar la privacidad frente al User-Agent tradicional.
Permite al servidor adaptar el contenido de forma más controlada.

