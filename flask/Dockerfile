FROM python:3.9.5-slim

COPY pip.conf /root/.pip/pip.conf

COPY app.py /src/

RUN pip3 install flask redis && \
    groupadd -r flask && useradd -r -g flask flask && \
    chown -R flask:flask /src

USER flask

WORKDIR /src/

ENV FLASK_APP=app.py

EXPOSE 5000

CMD ["flask", "run", "-h", "0.0.0.0"]
