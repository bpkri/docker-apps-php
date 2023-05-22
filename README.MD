# PHP 7.4 Dev Env

Versi comot-comot Laravel Sail

## Build Images

```sh
> docker compose build php74-dev # laravel < 8
> docker compose build php81-dev
```

## Running

- put your app inside `src/`
- create new nginx config in `conf/`
- add new nginx config in web section in `docker-compose.yml`
- run `docker compose up -d`
- open browser, http://localhost:8000

## HTTPS Access

- install [mkcert](https://github.com/FiloSottile/mkcert)
- `cd conf/certs && mkcert app.local`