# Análisis de Peticiones y Respuestas HTTP con HTTP Header
--- 

## Parte 1: Instalación y configuración

### Instalación de la extensión
Se ha instalado la extension **HTTP Header** en el navegador **Brave**, la cual permite capturar y analizar el tráfico HTTP generado durante la navegación web.

![Captura extensión instalada](/img/ExtencionInstalada.png)

## Parte 2: Captura de peticiones HTTP
Para esta parte se ha activado la captura de tráfico HTTP mediante la extensión **HTTP Header**
y se ha navegado a tres URLs distintas del mismo dominio.

## URL A: https://librebits.info

### Petición HTTP capturada

![Captura URL A](/img/CapturaGET-200.png)

## URL B: https://librebits.info/404

### Petición HTTP capturada

![Captura URL B](/img/CapturaGET-404.png)

## URL C: https://docs.google.com/forms/u/0/d/e/1FAIpQLSezxy_6IX8cr0QFflO0ZODlYyrLoV8YGdUl7Dw55It-O03Tpw/formResponse

### Peticion HTTP capturada

![Captura URL C](/img/CapturaPOST.png)

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

## Parte 3: Fotografía de las característa DNS del sitio Web

### Petición GET - 200

![URL A](/img/CapturaGET-200-2.png)


### Petición GET - 404

![URL B](/img/CapturaGET-404-2.png)

## Análisis de los elementos capturados:

**Date**: Permite concoer el momento exacto en el que se produca la respuesta

**Server**: Proporciona información sobre la tecnologóa usada por el servidor.

**Content-Type**: Indica el formate del mensaje de error devuelto al cliente.

**Keep-Alive**: Es una cabecera que permite mantener abierta la conexión TCP entre el cliente y el servidor después de una petición HTTP.

**Pragma**: Se utiliza principalmente con el valor no-cache para indircar que la respuesta no debe almacenarse.

### DNS Lookup de librebits.info 

![DNS librebits](/img//Librebit-DNS.png)

### Informacion del DNS

**Parent nameservers**: Indica los servidores DNS superiores responsables del dominio.

En este caso, pertenecen a Gandi.net, lo que significa que el dominio está gestionado por este proveedor

**NS**: Los registros NS definen los servidores autoritativos del dominio.

La coincidencia entre los NS del dominio y los del nivel padre confirma una configuración DNS correcta y coherente.

**SPF**: Este registro define qué servidores están autorizados a enviar correos en nombre del dominio, ayudando a prevenir la suplantanción de identidad.


**ASN**: El sistema autónomo asociado es AS60781, correspondiente a LeaseWeb Netherlands B.V. Esto identifica la red a la que pertenece al servidor y su proveedor de conectividad.

## Parte 4: Comparación con otros recursos

### Petición a un PNG

![Captura png](/img/CapturaAdicional-1.png)

### Petición a un CSS

![Captura css](/img/CapturaAdicional-2.png)

### Diferencias en el Content-Type

**PNG**: Su Content-Type es **image/png**. Este indica que el recurso es una imagen binaria que el navegador debe decodificar y mostrar visualmente, no interpretar como texto.

**CSS**: Su Content-Type es **text/css**. Señala que el recurso es un archivo de texto que contiene reglas de estilo que el navegador dane interpretar y aplicar al documento  HTML.