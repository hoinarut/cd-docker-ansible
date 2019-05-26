FROM hoinarut/todobackend-base:latest
LABEL maintainer="Tudor Hoinaru"

RUN apt update && \
    apt install -qy python3-dev libmysqlclient-dev

RUN . /appenv/bin/activate && \
    pip3 install wheel --upgrade

ENV WHEELHOUSE=/wheelhouse PIP_WHEEL_DIR=/wheelhouse PIP_FIND_LINKS=/wheelhouse XDG_CACHE_HOME=/cache

VOLUME /wheelhouse

VOLUME /reports

COPY scripts/test.sh /usr/local/bin/test.sh
RUN chmod +x /usr/local/bin/test.sh

ENTRYPOINT ["test.sh"]
CMD ["python3", "manage.py", "test", "--noinput"]

COPY src /application
WORKDIR /application