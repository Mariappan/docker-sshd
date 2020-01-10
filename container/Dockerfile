FROM       alpine:3.11
MAINTAINER Mariappan Ramasamy

RUN echo "root:root" | chpasswd \
    && apk add --update --no-cache openssh-server \
    && rm  -rf /tmp/* /var/cache/apk/*

COPY sshd_config /etc/ssh/sshd_config
RUN rm -rf /etc/ssh/ssh_host*

EXPOSE 22

CMD    ["/usr/sbin/sshd", "-De"]
