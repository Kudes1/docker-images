# Caddy-rate-limit

Стандартный сaddy:latest с плагином rate-limit

## Dockerfile

С помощью Dockerfile вы можете собрать образ самостоятельно

## Pull
`docker pull ghcr.io/kudes1/caddy-rate-limit:1.0`

## Запуск
Требуется пробросить ваш Caddyfile в контейнер по пути `/etc/caddy/Caddyfile`, так же лучше пробросить папки `/data` и `/config` (пример в docker-compose.yaml)

## Пример docker-compose.yaml
```
services:
  caddy-custom:
    build:
      context: .
      dockerfile: Dockerfile
    image: caddy-rate-limit:latest
    container_name: caddy-container
    volumes:
      - ./Caddyfile:/etc/caddy/Caddyfile
      - ./data:/data
      - ./config:/config
    restart: unless-stopped
    network_mode: host
```