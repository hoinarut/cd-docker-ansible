FROM ubuntu:trusty

ENV TERM=xterm-256color

RUN apt update -qy && \
    apt install -qy software-properties-common && \
    apt-add-repository -y ppa:ansible/ansible && \
    apt update -qy && \
    apt install -qy ansible

VOLUME /ansible
WORKDIR /ansible

ENTRYPOINT ["ansible-playbook"]
CMD ["site.yml"]
