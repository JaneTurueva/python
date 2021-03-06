FROM snakepacker/python:base

ENV PYTHONDONTWRITEBYTECODE=True

# Install headers for useful libraries
RUN apt-get update && apt-get install -y \
        git-core \
        build-essential && \
    rm -fr /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y \
        virtualenv \
        python \
        python-dev \
        python-pip \
        python-setuptools \
        python-wheel && \
    rm -fr /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y \
    python3.6 \
    python3.6-dev \
    python3-setuptools \
    python3-wheel \
    python3-pip && \
    rm -fr /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y python2.3 python2.3-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python2.4 python2.4-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python2.5 python2.5-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python2.6 python2.6-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python3.1 python3.1-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python3.2 python3.2-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python3.3 python3.3-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python3.4 python3.4-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python3.5 python3.5-dev && rm -fr /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y python3.7 python3.7-dev && rm -fr /var/lib/apt/lists/*

RUN pip3 install tox coveralls && \
    ln -snf /usr/local/bin/tox /usr/bin/tox && \
    ln -snf /usr/local/bin/coveralls /usr/bin/coveralls && \
    chmod a+x /usr/bin/tox /usr/bin/coveralls

ENV PIP_CONFIG_FILE /etc/pip.conf

RUN mkdir -p /var/cache/pip
ENV PIP_DOWNLOAD_CACHE=/var/cache/pip

COPY wait-for-port.py /usr/bin/wait-for-port
RUN chmod a+x /usr/bin/wait-for-port