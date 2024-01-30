FROM ubuntu:24.04

RUN apt-get update && \
    apt-get install -y openssh-server && \
    rm -rf /var/lib/{apt,dpkg,cache,log}

RUN useradd -rm -d /home/sshuser -s /bin/bash -g root -G sudo -u 1001 sshuser && \
    mkdir -p /var/run/sshd

# Change password if you want
RUN echo 'sshuser:password' | chpasswd

EXPOSE 22

CMD [ "/usr/sbin/sshd", "-D" ]