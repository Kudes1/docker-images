FROM caddy:builder AS builder

# Добавляем нужные плагины
RUN xcaddy build \
    --with github.com/mholt/caddy-ratelimit

# Используем финальный образ для запуска
FROM caddy:latest

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
