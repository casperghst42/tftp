# tftp
Simple Docker TFTP server - which allows file upload

Based on https://github.com/pghalliday-docker/tftp

docker build --rm -t casperghst42/tftp .

To Run:
```
docker run -p 69:69/udp -i -t pghalliday/tftp
```

Docker-compose
```
version: '3'

services:
    tftp:
        image: casperghst42/tftp:latest
        hostname: tftp
        container_name: tftp
        volumes:
            - tftp-data:/var/tftpboot
            - /etc/localtime:/etc/localtime:ro
        environment:
            - TZ=Europe/Berlin
        ports:
            - "69:69/udp"
```
