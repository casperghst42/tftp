FROM alpine:latest
RUN apk add --no-cache tftp-hpa
RUN chown nobody /var/tftpboot && chmod 775 /var/tftpboot
VOLUME /var/tftpboot
EXPOSE 69/udp
ENTRYPOINT ["in.tftpd"]
CMD ["-L", "-cs", "/var/tftpboot"]
