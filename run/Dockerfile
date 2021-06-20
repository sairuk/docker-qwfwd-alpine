FROM debian:stretch-slim
MAINTAINER sairuk
ARG SRVUSER=qw
ARG SRVUID=1004
ARG INSTDIR=/srv/qwfwd

RUN apt-get -y update \
&& apt-get -y upgrade

# CLEAN IMAGE
RUN apt-get -y clean && apt-get -y autoremove


# CREATE USER
RUN useradd -m -s /bin/bash -u ${SRVUID} ${SRVUSER} -d ${INSTDIR}

# SERVER FILES
COPY _server/. ${INSTDIR}
RUN chown -R ${SRVUSER}: ${INSTDIR}

EXPOSE \
# -- gameport
30000/udp \
27000/udp \
27000/tcp

# WORKING USER
#
USER ${SRVUSER}
WORKDIR ${INSTDIR}

CMD ["./qwfwd.bin"]


