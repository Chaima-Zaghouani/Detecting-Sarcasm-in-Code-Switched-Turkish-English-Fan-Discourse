FROM ghcr.io/davidjurgens/potato:latest

WORKDIR /app

COPY . /app

ENV POTATO_CONFIG=config.yaml

USER root
RUN pip install --no-cache-dir huggingface_hub

EXPOSE 8000
