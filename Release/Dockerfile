FROM python:3-alpine
LABEL maintainer="kmdgeek"

RUN apk --no-cache add ffmpeg \
 && pip3 install --no-cache-dir you-get \
 && mkdir -p /download

WORKDIR /download

ENTRYPOINT [ "you-get" ]
CMD [ "--help" ]
