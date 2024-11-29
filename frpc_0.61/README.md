# Frpc_0.61
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

## Примеры docker-compose.yaml

### Для запуска одного конфига:
```
services:
  frpc:
    image: ghcr.io/kudes1/frpc_0.61:${ARCH}
    container_name: frpc
    volumes:
      ./frpc_config.toml:/etc/frpc/config.toml
    restart: unless-stopped
    network_mode: host
```

### Для запуска нескольких конфигов:
```
services:
  frpc:
    image: ghcr.io/kudes1/frpc_0.61:${ARCH}
    container_name: frpc
    volumes:
      - ./frpc_config1.toml:/etc/frpc/config1.toml
      - ./frpc_config2.toml:/etc/frpc/config2.toml
    restart: unless-stopped
    network_mode: host
    command:
      '--config-dir /etc/frpc'
```