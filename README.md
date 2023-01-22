# Docker - Laravel

Un flujo de trabajo de Docker Compose bastante simplificado que configura una red de contenedores LEMP (Linux, NGINX, MySQL, PHP, mailhog) para el desarrollo local de Laravel.

## Puertos

Puertos utilizados en el proyecto:
| Software | puerto |
|-------------- | -------------- |
| **nginx** | 8080 |
| **phpmyadmin** | 8081 |
| **mysql** | 3306 |
| **php** | 9000 |
| **xdebug** | 9001 |
| **redis** | 6379 |
| **mailhog** | 8025 |

## Use

Para comenzar, asegúrese de tener [Docker instalado](https://docs.docker.com/) en su sistema y [Docker Compose](https://docs.docker.com/compose/install/), y luego clone este repositorio.

1. Clone this project:

   ```sh
   git clone pendiente
   ```

2. Dentro de la carpeta `docker-laravel-up` y Genere su propio `.env` para docker compose con el siguiente comando:

   ```sh
   cp .env.example .env
   ```

3. Necesitas **Crear** o **Poner** tu proyecto laravel en la fuente de la carpeta; para crear siga las siguientes instrucciones [Aquí] (source/README.md).

4. Cree el proyecto con los siguientes comandos:

   ```sh
   docker-compose up --build
   ```

---

## Remember

La configuración de la base de datos **debe ser la misma en ambos lados**.

```dotenv
# .env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_name
DB_USERNAME=db_user
DB_PASSWORD=db_password
DB_ROOT_PASSWORD=secret
```

```dotenv
# source/.env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=db_name
DB_USERNAME=db_user
DB_PASSWORD=db_password
```

El único cambio es `DB_HOST` en `source/.env` donde se llama al contenedor de `mysql`:

```dotenv
# source/.env
DB_HOST=mysql
```

---

## Casos especiales

Para Bajar y quitar los volúmenes usamos el siguiente comando:

```sh
docker-compose down -v
```

Update Composer:

```sh
docker-compose run --rm composer update
```

Ejecute el compilador (Webpack.mix.js) o muestre el compilador de vistas en el nodo:

```sh
docker-compose run --rm npm run dev
```

Ejecutar todas las migraciones:

```sh
docker-compose run --rm artisan migrate
```

## Adaptado de [supermavster](https://github.com/supermavster/docker-laravel-8)
