# Frpc_0.59
Образ собран на базе Alpine 3.20

## Dockerfile
С помощью Dockerfile вы можете собрать образ самостоятельно.
Требуется исполняемый файл frpc.

## ARCH
Поддерживыемые архитекруты:
+ amd64
+ arm64
+ arm32

## Pull
`docker pull ghcr.io/kudes1/frpc_0.59:${ARCH}`

## Запуск
Требуется пробросить файл конфигурации .toml в контейнер по пути `/etc/frpc/config.toml` (пример в docker-compose.yaml)

## Пример docker-compose.yaml
```
services:
  frpc:
    image: ghcr.io/kudes1/frpc_0.59:${ARCH}
    container_name: frpc
    volumes:
      ./frpc_config.toml:/etc/frpc/config.toml
    restart: unless-stopped
    network_mode: host
```