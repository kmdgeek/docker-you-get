FROM python:3-alpine
LABEL maintainer="kmdgeek"

RUN apk --no-cache add build-base git ffmpeg mpv \
 && pip3 install --no-cache-dir --upgrade git+https://github.com/zhangn1985/ykdl@master \
 && apk del build-base git \
 && mkdir -p /download

WORKDIR /download

ENTRYPOINT [ "ykdl" ]
CMD [ "--help" ]

