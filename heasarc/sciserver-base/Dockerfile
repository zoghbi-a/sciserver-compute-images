FROM ubuntu:24.04

RUN usermod -l idies -m -d /home/idies ubuntu \
    && groupmod -n idies ubuntu \
    && gpasswd -d idies sudo \
    && usermod -d /home/idies idies \
    && mkdir -p /home/idies/workspace \
    && chown -R idies:idies /home/idies

ARG DEBIAN_FRONTEND=noninteractive

RUN ln -fs /usr/share/zoneinfo/America/New_York /etc/localtime \
    && apt-get update \
    && apt-get install -y \
        build-essential \
        cmake \
        sudo \
        wget \
        curl \
        git \
        vim \
        htop \
        locales \
    && rm -rf /var/lib/apt/lists/* \
    && locale-gen "en_US.UTF-8" \
    && update-locale "LANG=en_US.UTF-8"

# RUN apt-get update \
#     && apt-get install -y texlive-full \
#     && rm -rf /var/lib/apt/lists/*
    