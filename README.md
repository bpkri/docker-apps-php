# Container for PHP project

Versi comot-comot Laravel Sail. Bedanya:

- satu docker compose untuk semua aplikasi. docker service-nya sebanyak versi php yang berbeda, bukan sebanyak aplikasi.
- tidak perlu install Laravel Sail di aplikasi

## Configuration

- determine your project shortname, eg. `eppid`. no space.
- put PHP source files inside `./src/eppid/`.
- create nginx config file, `conf/sites/eppid.conf`
- install [mkcert](https://github.com/FiloSottile/mkcert/releases) then create cert, `cd conf/certs && mkcert eppid.local`
- in `docker-compose.yml`, add new volume entry in `web` service: 
    `- ./conf/sites/app.conf:/etc/nginx/conf.d/default.conf`
- run `docker compose up -d`
- in  your local`etc/hosts`, add new line eg. `127.0.0.1  eppid.local`
- open http://eppid.local in browser

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

## Referensi/Tutorial

- [Slide ttg container/k8s/gw dll](https://docs.google.com/presentation/d/1vRfMbceoH00sv1bn2de5HNxmliQQiazzoSmD3gSXblE/edit?usp=sharing)
