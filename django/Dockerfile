FROM ubuntu:20.04

ADD . /app
WORKDIR /app

RUN apt-get update -y
RUN apt-get install software-properties-common -y
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get install python3-pip netcat -y
RUN python3 -m pip install --upgrade setuptools
RUN apt-get install sudo ufw build-essential libpq-dev libmysqlclient-dev python3-dev default-libmysqlclient-dev libpython3-dev -y
RUN python3 -m pip install -r requirements.txt
RUN python3 -m pip install django
RUN python3 -m pip install gunicorn
RUN python3 -m pip install psycopg2-binary
RUN sudo ufw allow 8000

#RUN sed -i 's/\r$//g' /app/entrypoint.sh
#RUN chmod +x /app/entrypoint.sh

EXPOSE 8000

# run entrypoint.sh
RUN ./entrypoint.sh

