FROM python:3.12

LABEL org.opencontainers.image.source=https://github.com/mjsully/docker-glances

RUN pip3 install py3nvml
RUN pip3 install glances==3.4.0.5
RUN pip3 install prometheus_client
RUN pip3 install glances[gpu,containers,graph,ip,web]