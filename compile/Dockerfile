FROM alpine:3.14
MAINTAINER sairuk
ARG USER=builduser
ARG UID=1004
ARG BS=build-script
ARG BSD=/tmp/${BS}


RUN apk add --no-cache \
      git \
      make \
      libc-dev \
      gcc

RUN adduser -D -s /bin/sh -u ${UID} ${USER}

COPY ${BS} ${BSD}

RUN chown ${USER}: ${BSD} \
    && chmod +x ${BSD}

VOLUME /home/${USER}
USER ${USER}
WORKDIR /home/${USER}

CMD /tmp/build-script

