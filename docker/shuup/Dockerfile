FROM ubuntu:16.04

COPY loop.sh /tmp/loop.sh

RUN apt-get update && \
    apt-get install -y software-properties-common iputils-ping net-tools && \
    add-apt-repository -y ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y python3.6 python3-pip python3-venv python-dev libssl-dev libffi-dev vim && \
    pyvenv-3.5 /tmp/shuup && \
    cd /tmp/shuup && . ./bin/activate && \
    pip3 install wheel && \
    pip3 install shuup && \
    pip3 install easy-thumbnails django-filer django-registration-redux django-bootstrap3 djangorestframework django-notifications-hq && \
    chmod 755 /tmp/loop.sh

CMD /tmp/loop.sh
