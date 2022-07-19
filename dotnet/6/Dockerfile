FROM        mcr.microsoft.com/dotnet/aspnet:6.0

LABEL       author="Brendan van Zyl" maintainer="brendanv@gmail.com"

ENV         DEBIAN_FRONTEND noninteractive
RUN         useradd -m -d /home/container -s /bin/bash container
RUN         ln -s /home/container/ /nonexistent
ENV         USER=container HOME=/home/container
USER        container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
