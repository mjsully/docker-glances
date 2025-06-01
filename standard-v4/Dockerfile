FROM python:3.12-alpine

LABEL org.opencontainers.image.source=https://github.com/mjsully/docker-glances

RUN apk add \
    gcc \
    musl-dev \
    libc-dev \
    python3-dev \
    linux-headers
COPY requirements.txt .
RUN pip3 install -r requirements.txt
COPY glances.conf /etc/glances.conf