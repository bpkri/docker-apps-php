# Container for PHP project

Versi comot-comot Laravel Sail

## Build Images

```sh
> docker compose build php74-dev # eg. laravel < 8
> docker compose build php81-dev
```

## Configuration

- put your app inside `src/`
- create new nginx config in `conf/sites/`
- add new nginx config in web section in `docker-compose.yml`
- run `docker compose up -d`
- modify etc/hosts local, add site domain
- open browser, http://site.domain

## Running

If you want to 'activate' project EPPID, you need to update environment variable

```sh
cd $THIS_README_DIR
export APP=eppid
export APP_SERVICE=php81
```

## HTTPS Access

- install [mkcert](https://github.com/FiloSottile/mkcert)
- `cd conf/certs && mkcert site-domain`
