FROM debian:9.4-slim

RUN apt-get update -y && apt-get install -y python python-psycopg2 python-pip python-flask python-six && \
    pip install cryptography eventlet boto3 google-cloud-storage future bcrypt pycrypto \
    azure-mgmt-resource azure-storage keystoneauth1==3.7.0 python-swiftclient && \
    apt-get remove -y python-pip && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/*

COPY src/gc gc
COPY src/pyinfraboxutils /pyinfraboxutils

ENV PYTHONPATH=/

CMD python gc/gc.py
