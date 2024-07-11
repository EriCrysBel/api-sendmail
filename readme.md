# API de Envío de Correos en PHP
Una API  escrita en PHP que permite enviar correos a un administrador
## Requisitos
- PHP 
- XAMPP

### Instalación
 - Clonar repositorio de Github
````
git clone https://github.com/tu-usuario/tu-repositorio.git

````
### Configuración
- Abre el archivo index.php y configura el correo del webmaster en la variable $webmaster_email
````
$webmaster_email = 'erikacrystal95@gmail.com';

````
### Uso
- Inicia XAMPP.
Envía una solicitud POST al script con el siguiente formato JSON:
````
{
    "name": "Tu Nombre",
    "email": "tuemail@example.com",
    "message": "Tu mensaje"
}

````