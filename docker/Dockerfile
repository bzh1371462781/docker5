ROM node:lts-alpine
LABEL maintainer="clamp <imclamp@foxmail.com>"
ARG ASM_SCRIPTS_URL=https://github.com/bzh1371462781/docker6
ARG ASM_SCRIPTS_BRANCH=main
ARG ASM_WRAPPER_URL=https://github.com/bzh1371462781/docker5
ARG ASM_WRAPPER_BRANCH=main
ARG enable_unicom=true
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
    LANG=zh_CN.UTF-8 \
    SHELL=/bin/bash \
    PS1="\u@\h:\w \$ " \
    ASM_SCRIPTS_BRANCH=azmodan \
    ASM_DIR=/AutoSignMachine
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update -f \
    && apk upgrade \
    && apk --no-cache add -f bash \
    coreutils \
    moreutils \
    git \
    wget \
    curl \
    nano \
    tzdata \
    perl \
    openssl \
    libav-tools \
    libjpeg-turbo-dev \
    libpng-dev \
    libtool \
    libgomp \
    tesseract-ocr \
    graphicsmagick \
    && rm -rf /var/cache/apk/* \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    && git clone -b ${ASM_WRAPPER_BRANCH} ${ASM_WRAPPER_URL} ${ASM_DIR} \
    && git clone -b ${ASM_SCRIPTS_BRANCH} ${ASM_SCRIPTS_URL} ${ASM_DIR}/scripts \
    && cd ${ASM_DIR}/scripts \
    && npm install \
    && cp -f ${ASM_DIR}/docker/entrypoint.sh /entrypoint.sh \
    && chmod 777 /entrypoint.sh

WORKDIR ${ASM_DIR}
