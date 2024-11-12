ARG ALPINE_VERSION="3.20"
ARG SHADOW_VERSION="4.15.1-r0"
ARG TZDATA_VERSION="2024b-r0"
ARG TZ="America/Los_Angeles"

FROM alpine:3.20

USER root

RUN apk update && \
	apk add --no-cache "shadow=${SHADOW_VERSION}" "tzdata=${TZDATA_VERSION}"
ENV TZ=${TZ}

USER guest

ARG BUILD_DATE

# Standardized labels
LABEL org.opencontainers.image.created=${BUILD_DATE}
LABEL org.opencontainers.image.authors="Darrell Dudics <public-docker@radtechdad.com>"
LABEL org.opencontainers.image.url="https://hub.docker.com/repository/docker/radtechdad/alpine"
LABEL org.opencontainers.image.documentation="https://github.com/radtechdad-docker-images/alpine/blob/main/README.md"
LABEL org.opencontainers.image.source="https://github.com/example/source"
