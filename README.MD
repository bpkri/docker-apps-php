# Container for PHP project

Versi comot-comot Laravel Sail. Bedanya:

- satu docker compose untuk semua aplikasi. docker service-nya sebanyak versi php yang berbeda, bukan sebanyak aplikasi.
- tidak perlu install Laravel Sail di aplikasi

## Configuration

0. determine your project shortname, eg. `eppid`. no space.
1. put PHP source files inside `./src/eppid/`.
2. create nginx config file, `conf/sites/eppid.conf`
3. in `docker-compose.yml`, add new volume entry in `web` service: 
    `- ./conf/sites/app.conf:/etc/nginx/conf.d/default.conf`
4. run `docker compose up -d`
5. in  your local`etc/hosts`, add new line eg. `127.0.0.1  eppid.local`
6. open http://eppid.local in browser

## Development

When using `Laravel Sail`, you can use `sail` cli to run shell, php, composer, npm, etc inside app container on the project folder. Using this project, you must set active app first.

```sh
$ cd $THIS_README_DIR
$ source ./bin/active eppid
$ ./bin/sail --help
```

### Application configuration


## HTTPS Access

- install [mkcert](https://github.com/FiloSottile/mkcert)
- `cd conf/certs && mkcert site-domain`

## Build Images

```sh
> docker compose build php74 # eg. laravel < 8
> docker compose build php81
```
