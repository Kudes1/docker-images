FROM alpine:3.20

COPY frpc /usr/local/bin/frpc

RUN chmod +x /usr/local/bin/frpc

ENTRYPOINT ["frpc"]

CMD ["-c", "/etc/frpc/config.toml"]