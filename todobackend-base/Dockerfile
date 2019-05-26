FROM ubuntu:18.04
LABEL maintainer="Tudor Hoinaru"

ENV TERM=xterm-256color

RUN apt update && \
    apt -y upgrade && \
    apt install -y \
    -o APT::Install-Recommend=false -o APT::Install-Sugests=false \
    python3-pip && \
    pip3 install virtualenv

RUN virtualenv /appenv && \
    . /appenv/bin/activate && \
    pip3 install pip --upgrade

ADD scripts/entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh
ENTRYPOINT [ "entrypoint.sh" ]