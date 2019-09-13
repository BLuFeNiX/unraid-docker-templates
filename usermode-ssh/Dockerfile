FROM alpine:3.9

RUN apk add --no-cache openssh-server openssh bash

RUN ssh-keygen -t rsa -N "" -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -t ecdsa -N "" -f /etc/ssh/ssh_host_ecdsa_key
RUN ssh-keygen -t ed25519 -N "" -f /etc/ssh/ssh_host_ed25519_key

RUN echo "Welcome to Unraid SSH" > /etc/motd

RUN adduser chase -D
RUN echo "chase:chase" | chpasswd

#ENTRYPOINT [ "/bin/bash" ]
CMD [ "/usr/sbin/sshd", "-D" ]