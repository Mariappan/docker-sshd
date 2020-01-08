FROM       alpine:3.11
MAINTAINER Mariappan Ramasamy

RUN echo "root:root" | chpasswd \
    && apk add --update --no-cache openssh-server \
    && rm  -rf /tmp/* /var/cache/apk/*

RUN sed -ri 's/^#PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config \
&& sed -ri 's/^StrictModes\s+.*/StrictModes no/' /etc/ssh/sshd_config \
&& sed -ri 's/^GatewayPorts\s+.*/GatewayPorts yes/' /etc/ssh/sshd_config \
&& sed -ri 's/#HostKey \/etc\/ssh\//HostKey \/etc\/ssh\/hostKeys\//g' /etc/ssh/sshd_config \
&& echo "PasswordAuthentication no" >> /etc/ssh/sshd_config

RUN rm -rf /etc/ssh/ssh_host*

EXPOSE 22

CMD    ["/usr/sbin/sshd", "-De"]
