FROM ubuntu:18.04

ARG HHVM_REPO_DISTRO=bionic
ENV HHVM_DISABLE_NUMA true

# Hard-coded hhvm.deb URL sourced from Fred (at Facebook)
# https://hacklang.slack.com/archives/CAVPCQUQK/p1556651165014900

RUN \
  apt-get update -y && apt-get install -y software-properties-common apt-transport-https \
  && apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0x5a16e7281be7a449 \
  && apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xB4112585D386EB94 \
  && apt-get update -y \
  && DEBIAN_FRONTEND=noninteractive apt-get install -y git wget curl \
  && wget https://dl.hhvm.com/ubuntu/pool/main/h/hhvm/hhvm_3.25.3-1~bionic_amd64.deb \
  && DEBIAN_FRONTEND=noninteractive apt install -y ./hhvm_3.25.3-1~bionic_amd64.deb \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
