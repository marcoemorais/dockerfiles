FROM ubuntu:16.04
MAINTAINER Marco Morais "marcoemorais@yahoo.com"

WORKDIR /src

RUN apt-get update && apt-get install -y \
    octave \
    octave-info \
    less \
    && rm -rf /var/lib/apt/lists/*

CMD ["octave"]
