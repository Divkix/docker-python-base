ARG BASE_IMAGE
FROM ${BASE_IMAGE}
ENV DEBIAN_FRONTEND noninteractive
ENV TZ UTC
COPY tools/docker/setup /tmp/setup
RUN apt-get update \
    && apt-get upgrade --yes \
    && apt-get install --no-install-suggests --no-install-recommends --yes \
    apt-utils \
    build-essential \
    libpq-dev \
    python3-dev \
    python3-lxml \
    gcc \
    g++ \
    wget \
    curl \
    xz-utils \
    gzip \
    git \
    make \
    unzip \
    zip \
    apt-transport-https \
    ca-certificates \
    gnupg \
    && pip install --no-cache-dir --upgrade poetry \
    && poetry config virtualenvs.in-project true \
    && apt-get clean \
    && apt-get autoremove --purge --yes \
    && /tmp/setup/ffmpeg-setup.sh \
    && rm -rf /var/lib/apt/lists/* /root/* /tmp/* /var/cache/apt/archives/*.deb /tmp
LABEL org.opencontainers.image.authors="Divanshu Chauhan <divkix@divkix.me>"
LABEL org.opencontainers.image.url="https://divkix.me"
LABEL org.opencontainers.image.source="https://github.com/Divkix/docker-python-base"
LABEL org.opencontainers.image.title="docker-python-base"
LABEL org.opencontainers.image.description="Base python 🐍 image for building python applications 📲"
LABEL org.opencontainers.image.vendor="Divkix"
