FROM debian:bookworm-slim

WORKDIR /work

ENV DEBIAN_FRONTEND=noninteractive

ARG TARGETPLATFORM

ARG BUILDPLATFORM

RUN apt update && apt upgrade -y

RUN apt install -y mc less netcat-openbsd emacs-nox

RUN apt install -y dialog python3 python3-pip python3-venv build-essential

RUN echo "$TARGETPLATFORM" >/platform

#RUN if [ "$TARGETPLATFORM" = "linux/arm64" ]; then echo arm | tee -a ../ap; fi

#RUN if [ "$TARGETPLATFORM" = "linux/amd64" ]; then echo x86 | tee -a ../ap; fi

RUN cd / && python3 -m venv venv

RUN . /venv/bin/activate && pip install rich requests

#COPY src/PYMOD /venv/lib/python3.11/site-packages/PYMOD

RUN apt update && apt upgrade -y

RUN apt install -y gnupg curl uuid-runtime

COPY src/startup.sh /startup.sh

COPY src/usr/local/bin/jput /usr/local/bin/jput
COPY src/usr/local/bin/jcat /usr/local/bin/jcat

COPY src/app /app

ENV PWHISPER_HOME=/work

CMD [ "/bin/bash", "/startup.sh" ]
