# Nginx 1.19.6 + Quic Http/3

---

## Dockerfile

[Docker Hub](https://hub.docker.com/r/richnet/nginx)

[peter10216/nginx-quic](https://github.com/peter10216/nginx-quic)

Based on Ubuntu 20.04 with Nginx `1.19.6`

Main function is in below: 

- http/3 quic , 0-RTT , TLSv1.3
- headers-more-nginx-module
- Google brotli
- qzip

## docker-compose.yml

This project is running by docker-compose yml file

volumes content extra conf file

### quic.conf

- add quic header
- listen 443 udp port

### TLC1_3.conf

- enable ssl protocols : TLS v1.2 & 1.3
- enable ssl_prefer_server_ciphers
- enable ssl_session_tickets
- enable ssl_ciphers : `TLS13-AES-256-GCM-SHA384:TLS13-CHACHA20-POLY1305-SHA256:TLS13-AES-128-GCM-SHA256:TLS13-AES-128-CCM-8-SHA256:HIGH:!aNULL:!MD5;`

### BLOCK.conf

- Exchange `Server` header, default header `richnet.tw`
- Block common web bots or worms
