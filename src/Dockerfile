FROM python:3.8.3-slim

RUN apt-get update 
RUN apt-get -y install libpq-dev gcc postgresql python3-dev musl-dev

RUN pip install --upgrade pip
RUN pip install uwsgi
COPY requirements.in .
RUN pip install -r requirements.in

COPY . .
CMD uwsgi --http "0.0.0.0:8000" --module app.wsgi
