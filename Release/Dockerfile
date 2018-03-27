FROM python:3-alpine
LABEL maintainer="kmdgeek"

RUN apk --no-cache add ffmpeg mpv \
 && pip3 install --no-cache-dir ykdl \
 && mkdir -p /download

WORKDIR /download

ENTRYPOINT [ "ykdl" ]
CMD [ "--help" ]
