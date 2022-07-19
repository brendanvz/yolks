FROM        mono:6.12.0.182-slim

LABEL       author="Brendan van Zyl" maintainer="brendanvz@gmail.com"

ENV         DEBIAN_FRONTEND noninteractive

RUN         useradd -m -d /home/container -s /bin/bash container

RUN         ln -s /home/container/ /nonexistent

ENV         USER=container HOME=/home/container

RUN         apt-get update \
            && apt-get install -y binutils curl mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl \
            && rm -rf /var/lib/apt/lists/* /tmp/*

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
