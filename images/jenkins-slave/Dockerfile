FROM ubuntu:18.04

ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000

RUN groupadd -g ${gid} ${group}
RUN useradd -c "Jenkins user" -d /home/${user} -u ${uid} -g ${gid} -m ${user}

ARG AGENT_WORKDIR=/home/${user}/agent

RUN apt-get update && apt-get install -y \
  cmake \
  git \
  build-essential \
  python3-dev

USER ${user}
ENV AGENT_WORKDIR=${AGENT_WORKDIR}
RUN mkdir -p /home/${user}/.jenkins ${AGENT_WORKDIR} /home/${user}/artifact

VOLUME /home/${user}/artifact
WORKDIR /home/${user}
