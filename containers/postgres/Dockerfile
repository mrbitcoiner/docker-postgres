FROM postgres:15.2-bullseye

ARG CONTAINER_USER
ARG POSTGRES_PASSWORD
ARG HOST_UID
ARG HOST_GID

ENV POSTGRES_USER=${CONTAINER_USER}
ENV POSTGRES_PASSWORD=${POSTGRES_PASSWORD}

COPY ./volume/scripts /scripts

RUN /scripts/user_setup.sh "${CONTAINER_USER}" "${HOST_UID}" "${HOST_GID}"

ENTRYPOINT ["/scripts/init.sh"]

