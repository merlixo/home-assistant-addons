ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN apk add --no-cache tzdata jq openssh vim curl autossh

RUN apk update \
    && apk add --no-cache tzdata jq openssh vim curl autossh sudo \
    && adduser -D yourusername \
    && addgroup yourusername wheel \
    && echo "%wheel ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
