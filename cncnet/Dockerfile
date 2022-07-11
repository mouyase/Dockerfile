FROM debian:stretch-slim
WORKDIR /root/cncnet

ENV TZ=Asia/Shanghai
RUN rm -rf /etc/localtime && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get -y install wget libicu-dev && wget -c https://downloads.cncnet.org/cncnet-server.tgz -O - | tar -xz && apt-get clean && apt-get autoclean

ENV CNCSERVER_NAME=CNCNetServer
ENV CNCSERVER_MAX_PLAYER=128

CMD ./cncnet-server --name "$CNCSERVER_NAME" --maxclients $CNCSERVER_MAX_PLAYER --port 50001 --portv2 50000
