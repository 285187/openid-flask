FROM ubuntu:latest
LABEL maintainer="Igor Vieira https://github.com/imvieira"

RUN apt-get update && \
    apt-get install -y python3-pip python3-dev && \
    cd /usr/local/bin && \
    ln -s /usr/bin/python3 python && \
    pip3 install --upgrade pip && \
    apt-get clean;

EXPOSE 4443

COPY requirements.txt ./
RUN pip3 install --no-cache-dir -r requirements.txt
RUN pip3 install cryptography

WORKDIR /app
COPY . /app

RUN groupadd -r oidcgrp && useradd -r -g oidcgrp oidcusr
RUN chown -R oidcusr:oidcgrp /app
USER oidcusr

CMD ["python", "app.py"]
