FROM amd64/python:2.7.16-alpine

LABEL maintainer="Roxedus"
LABEL maintainer_contact="me@roxedus.dev"

ENV args=-h

RUN \
    echo "**** install build packages ****" && \
    python2 -m pip install requests configparser && \
    apk add --no-cache git && \
    echo "**** Clonig project ****" && \
    git clone -b master https://github.com/RhinoRhys/radarr-collections /app

COPY /folders.sh /run/folders.sh

CMD sh /run/folders.sh && python /app/rcm.py /config $args

VOLUME /config