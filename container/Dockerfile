FROM       alpine:3.11
MAINTAINER Mariappan Ramasamy

RUN adduser -D -h /home/span -u 1000 span && echo "span:span" | chpasswd
RUN apk add --update --no-cache openssh-server && rm -rf /etc/ssh/ssh_host*
COPY sshd_config /etc/ssh/sshd_config

EXPOSE 22

CMD    ["/usr/sbin/sshd", "-De"]
