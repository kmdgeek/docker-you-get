FROM python:3-alpine
LABEL maintainer="kmdgeek"

RUN apk --no-cache add ffmpeg git \
 && pip3 install --no-cache-dir --upgrade git+https://github.com/soimort/you-get@develop \
 && apk del git \
 && mkdir -p /download

WORKDIR /download

ENTRYPOINT [ "you-get" ]
CMD [ "--help" ]
