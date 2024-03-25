FROM debian:latest

RUN apt-get update && apt-get install -y\
    dnsmasq \
    ipxe

# IPXE setup 
RUN mkdir -p /tftpboot/menu
RUN cp /usr/lib/ipxe/ipxe.efi /tftpboot/
RUN cp /usr/lib/ipxe/undionly.kpxe /tftpboot/
COPY ./tftpboot/menu.ipxe /tftpboot/boot.ipxe

# dnsmasq setup
COPY ./dnsmasq.conf /etc/dnsmasq.conf

EXPOSE 67
CMD ["dnsmasq", "-d"]
