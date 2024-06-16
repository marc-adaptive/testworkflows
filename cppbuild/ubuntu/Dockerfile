FROM ubuntu:20.04 AS builder

ARG DEBIAN_FRONTEND=noninteractive

RUN adduser athena

ENV TZ=Etc/UTC
RUN apt-get update && apt-get install -y git

USER athena
WORKDIR /opt/aeron
ADD --chown=athena:athena . /opt/aeron

# without this +guilty will get added (stat entries in git index out of date after copying into a container):
RUN git update-index -q --refresh


FROM scratch as essential-artifacts

COPY --from=builder ./*.txt /