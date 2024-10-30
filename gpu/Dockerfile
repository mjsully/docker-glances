FROM python:3.12-alpine

LABEL org.opencontainers.image.source=https://github.com/mjsully/docker-glances

RUN apk add \
    gcc \
    musl-dev \
    libc-dev \
    python3-dev \
    linux-headers
RUN pip3 install py3nvml
RUN pip3 install glances==3.4.0.5
RUN pip3 install prometheus_client
RUN pip3 install glances[gpu,containers,graph,ip,web]

CMD ["glances", "-w"]