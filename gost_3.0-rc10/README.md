# Gost_3.0-rc10
Образ собран на базе Alpine 3.20

## Dockerfile
С помощью Dockerfile вы можете собрать образ самостоятельно.
Требуется исполняемый файл gost.

## ARCH
Поддерживаемые архитектуры:
+ amd64
+ arm64
+ arm32

## Pull
`docker pull ghcr.io/kudes1/gost_3.0-rc10:${ARCH}`

## Запуск
Требуется пробросить файл конфигурации .yaml в контейнер по пути `/etc/gost/config.yaml` (пример в docker-compose.yaml)

## Пример docker-compose.yaml
```
services:
  gost:
    image: ghcr.io/kudes1/gost_3.0-rc10:${ARCH}
    container_name: gost
    volumes:
      ./gost_config.yaml:/etc/gost/config.yaml
    restart: unless-stopped
    network_mode: host
```