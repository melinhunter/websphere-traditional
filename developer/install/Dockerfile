FROM ubuntu:16.04

Bishnu Roy <bishnuroy@gmail.com>

RUN apt-get update && apt-get install -y openssl wget

ARG USER=was
ARG GROUP=was
ARG TAR_URL

COPY start_server create_profile create_and_start modify_password \
  updateHostName.py updatePassword.py /work/

RUN groupadd $GROUP \
  && useradd $USER -g $GROUP -m \
  && chown -R $USER:$GROUP /work /opt

USER $USER

RUN wget -q -O - $TAR_URL | tar xz

ENV PATH /opt/IBM/WebSphere/AppServer/bin:$PATH

CMD ["/work/create_and_start"]
