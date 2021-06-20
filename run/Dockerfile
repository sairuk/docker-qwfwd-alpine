FROM alpine:3.14
MAINTAINER sairuk
ARG SRVUSER=qw
ARG SRVUID=1004
ARG INSTDIR=/srv/qwfwd

# CREATE USER
RUN adduser -D -s /bin/sh -h ${INSTDIR} -u ${SRVUID} ${SRVUSER} 

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


