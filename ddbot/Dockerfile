FROM alpine:latest
WORKDIR /ddbot

ENV VERSION=v1.0.8

RUN apk add --no-cache tzdata && cp -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2 && wget -c https://github.com/Sora233/DDBOT/releases/download/$VERSION/DDBOT-$VERSION-linux-amd64.tar.gz -O - | tar -xz && mv DDBOT /bin/DDBOT

CMD DDBOT
