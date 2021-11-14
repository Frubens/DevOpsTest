# syntax=docker/dockerfile:1

FROM python:3.6-slim-buster

WORKDIR /app

RUN groupadd -r fernando && useradd -r -g fernando fernando

COPY requirements.txt requirements.txt

RUN apt-get update -y && \
    apt-get install libpq-dev -y && \
    apt-get install python3-dev -y && \ 
    apt-get install libevent-dev -y && \
    apt-get install gcc -y
RUN pip3 install -r requirements.txt

COPY --chown=fernando:fernando todo-backend-flask/. .

USER fernando

EXPOSE 5000

ENV FLASK_APP=app.py

ENTRYPOINT [ "python3", "-m", "flask", "run", "--host=0.0.0.0" ]
