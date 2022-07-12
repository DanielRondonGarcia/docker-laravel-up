# Aquí es donde va tu aplicación Laravel

Agrega tu proyecto Laravel aquí (o crea uno nuevo en blanco).

---

**Note:** SI existen problemas para generar el proyecto, elimine este README.md

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

## Help

Una pequeña ayuda para crear el proyecto:

### Hacer un nuevo proyecto

```sh
docker-compose run --rm composer create-project laravel/laravel .
```

### Copiar Environment

```sh
cp .env.example .env
```

---

### Instalar bibliotecas desde Composer

```sh
docker-compose run --rm composer install
```

### Instalar bibliotecas desde el nodo

```sh
docker-compose run --rm npm install
```

### Clear/Clean el proyecto

```sh
docker-compose run --rm artisan clear:data
docker-compose run --rm artisan cache:clear
docker-compose run --rm artisan view:clear
docker-compose run --rm artisan route:clear
docker-compose run --rm artisan clear-compiled
docker-compose run --rm artisan config:cache
docker-compose run --rm artisan storage:link
```

### Generate Keys

```sh
docker-compose run --rm artisan key:generate
```

### Run migrations

```sh
docker-compose run --rm artisan migrate --seed
```

### Run Passport (Optional)

```sh
docker-compose run --rm artisan passport:install
```
