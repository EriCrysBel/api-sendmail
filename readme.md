# API de Envío de Correos en PHP
Una API  escrita en PHP que permite enviar correos a un administrador
## Requisitos
- Editor de código y plugin rest Client
- PHP 
- servidor de pruebas XAMMP
- Composer
- Cuenta en Github

### Instalación
 - Clonar repositorio de Github
```bash
git clone https://github.com/EriCrysBel/api-sendmail.git

```
### Configuración
- Abre el archivo index.php y configura el correo del webmaster en la variable $webmaster_email
```php
$webmaster_email = 'example@gmail.com';

```
### Uso
- Inicia XAMPP.
Envía una solicitud POST al script con el siguiente código en un archivo .http:
```http
POST  http://tu-dominio/api-erika/v1/endpoint-webservice/
Content-Type: "application/json"

{
    "name": "Tu Nombre",
    "email": "tuemail@example.com",
    "message": "Tu mensaje"
}

```
- En el cuerpo de la solicitud, envía los datos del formulario en formato JSON.
### Respuestas del servidor
- Introducimos todos los datos correctamente.
```http
POST  http://tu-dominio/api-erika/v1/endpoint-webservice/
Content-Type: "application/json"

{
    "name": "Tu Nombre",
    "email": "tuemail@example.com",
    "message": "Tu mensaje"
}

```
- Obtendremos la siguiente respuesta del servidor
```http
HTTP/1.1 200 OK
Date: Thu, 11 Jul 2024 08:59:30 GMT
Server: Apache/2.4.58 (Win64) OpenSSL/3.1.3 PHP/8.2.12
X-Powered-By: PHP/8.2.12
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: POST
Access-Control-Allow-Headers: Authorization, Content-Type
Content-Length: 62
Connection: close
Content-Type: application/json

{
  "status": "success",
  "message": "Correo enviado correctamente."
}

```
- Falta introducir alguno de los datos.
```http
POST  http://tu-dominio/api-erika/v1/endpoint-webservice/
Content-Type: "application/json"

{
    "name": "",
    "email": "tuemail@example.com",
    "message": "Tu mensaje"
}

```
- Obtendremos la siguiente respuesta del servidor
```http
HTTP/1.1 400 Bad Request
Date: Thu, 11 Jul 2024 09:01:00 GMT
Server: Apache/2.4.58 (Win64) OpenSSL/3.1.3 PHP/8.2.12
X-Powered-By: PHP/8.2.12
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: POST
Access-Control-Allow-Headers: Authorization, Content-Type
Content-Length: 49
Connection: close
Content-Type: application/json

{
  "status": "error",
  "message": "Datos incompletos."
}

```
- Se añade un email incorrecto (sin formato email).
```http
POST  http://tu-dominio/api-erika/v1/endpoint-webservice/
Content-Type: "application/json"

{
    "name": "",
    "email": "tuemailexample.com",
    "message": "Tu mensaje"
}

```
- Obtendremos la siguiente respuesta del servidor
```http
HTTP/1.1 400 Bad Request
Date: Thu, 11 Jul 2024 09:01:00 GMT
Server: Apache/2.4.58 (Win64) OpenSSL/3.1.3 PHP/8.2.12
X-Powered-By: PHP/8.2.12
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: POST
Access-Control-Allow-Headers: Authorization, Content-Type
Content-Length: 49
Connection: close
Content-Type: application/json

{
  "status": "error",
  "message": "Datos incompletos."
}

```