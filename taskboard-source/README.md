TaskBoard — Semana 7

Integración de Sistemas · UPED · Ciclo 02-2026

Docente: Ing. Oscar Armando Contreras
Tema: Eloquent ORM y modelo de datos

1. Descripción del proyecto

Este proyecto corresponde al trabajo de TaskBoard de la Semana 7.

En esta semana se trabaja principalmente con Eloquent ORM, utilizando modelos, migraciones y relaciones entre las entidades del sistema.

El proyecto maneja información de:

Comercios

Transacciones

Eventos de transacción

La estructura permite relacionar un comercio con sus transacciones y cada transacción con sus eventos.

2. Modelo de datos

La relación principal del proyecto es:

Comercio  1 ──< N  Transaccion  1 ──< N  EventoTransaccion

Comercio

Contiene información como:

nombre_comercio

rubro

telefono

Transaccion

Contiene:

comercio_id

monto

cliente_nombre

estado

Los estados utilizados son:

Iniciada

Completada

Fallida

EventoTransaccion

Contiene:

transaccion_id

tipo_evento

detalle

Esta entidad funciona como una bitácora relacionada con las transacciones.

3. Archivos principales de la Semana 7

Los archivos relacionados con el trabajo de Eloquent ORM incluyen:

app/
└── Models/
    ├── Comercio.php
    ├── Transaccion.php
    └── EventoTransaccion.php

database/
├── migrations/
│   ├── create_comercios_table.php
│   ├── create_transacciones_table.php
│   └── create_eventos_transaccion_table.php
│
└── seeders/
    ├── DatabaseSeeder.php
    └── ComercioSeeder.php

4. Requisitos previos

Antes de ejecutar el proyecto se recomienda tener instalado:

Herramienta

Versión mínima

Verificación

PHP

8.2

php -v

Composer

2.x

composer -V

MySQL / MariaDB

8.x / 10.x

mysql --version

Si utilizas Laravel Herd, XAMPP, Laragon o WAMP, algunas de estas herramientas pueden venir incluidas.

5. Instalación del proyecto

Si se parte de un proyecto Laravel limpio, primero se puede crear con:

composer create-project laravel/laravel taskboard
cd taskboard

Después se deben colocar los archivos del proyecto respetando la estructura de carpetas.

6. Configuración de la base de datos

Crear una base de datos llamada taskboard:

CREATE DATABASE taskboard CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

En el archivo .env configurar los datos de conexión:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=taskboard
DB_USERNAME=root
DB_PASSWORD=

Si tu instalación de MySQL utiliza otro usuario o contraseña, utiliza los datos correspondientes.

7. Migraciones y datos de prueba

Desde la carpeta principal del proyecto:

php artisan migrate

Para cargar los datos de ejemplo:

php artisan db:seed

También puede utilizarse:

php artisan migrate:fresh --seed

8. Ejecutar el proyecto

Para iniciar el servidor local:

php artisan serve

Normalmente se podrá acceder desde:

http://127.0.0.1:8000

9. Verificación

Antes de considerar terminado el proyecto, comprobar:

El proyecto inicia correctamente.

La conexión con MySQL funciona.

Las migraciones se ejecutan sin errores.

Los modelos de Eloquent están disponibles.

Las relaciones entre Comercio, Transaccion y EventoTransaccion funcionan.

Los datos de prueba se cargan correctamente.

10. Tecnologías utilizadas

PHP

Laravel

Eloquent ORM

MySQL / MariaDB

Composer

Blade

11. Autor

Jeni Corena

Integración de Sistemas · UPED · Ciclo 02-2026