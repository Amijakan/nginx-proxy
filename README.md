# nginx-proxy

[nginx-proxy/nginx-proxy](https://github.com/nginx-proxy/nginx-proxy)

## Goal
- Host multiple subdomains in one VPS
- SSL enabled
- With docker container for repeatability


## Preparation

- a working domain with DNS configured

## Adding an app to subdomain

1. copy docker-compose.app.yml to your desired app directory

`cp ./docker-compose.app.yml /path/to/your/app/`

1. Set up .env in that directory
1. run `docker-compose -f ./docker-compose.yml -f docker-compose.app.yml up -d`

```env
CONTAINER_APP_PORT= container's port number that 
HOST_APP_PORT= whichever open port you have
APP_DOMAIN_NAME= target domain to host
EMAIL=email for letsencrypt notification
```

