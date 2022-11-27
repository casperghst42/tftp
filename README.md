# tftp
Simple Docker TFTP server - which allows file upload

Based on https://github.com/pghalliday-docker/tftp

docker build --rm -t casperghst42/tftp .

To run:
```
docker run -v tftp-data:/var/tftpboot -p 69:69/udp -i -t casperghst42/tftp
```

Docker-compose
```yaml
version: '3'

services:
    tftp:
        hostname: tftp
        container_name: tftp
        build: .
        volumes:
            - tftp-data:/var/tftpboot
            - /etc/localtime:/etc/localtime:ro
        environment:
            - TZ=Europe/Berlin
        ports:
            - "69:69/udp"

volumes:
  tftp-data:
```

To run: 
```
docker-compose up
```