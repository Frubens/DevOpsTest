# syntax=docker/dockerfile:1

FROM python:3.6-slim-buster

WORKDIR /app

RUN groupadd -r fernando && useradd -r -g fernando fernando

RUN apt-get update -y 

COPY --chown=fernando:fernando . .

USER fernando

EXPOSE 9000

ENTRYPOINT [ "python3", "-m", "http.server", "9000" ]
