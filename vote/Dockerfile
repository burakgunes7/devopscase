FROM python:3

RUN mkdir /app

ADD . /app

WORKDIR /app

RUN pip install -r requirements.txt

EXPOSE 80:80

CMD [ "python", "app.py" ]