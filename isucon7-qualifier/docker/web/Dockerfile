FROM alpine AS build-dev

ARG GIT_URL=https://github.com/isucon/isucon7-qualify.git

RUN \
  apk --no-cache add git && \
  git clone --depth=1 $GIT_URL /isubata && \
  rm -rf /isubata/.git
#  apk --no-cache add wget && \
#  apk --no-cache add unzip && \
#  wget https://github.com/tkuchiki/alp/releases/download/v1.0.3/alp_linux_amd64.zip && \
#  unzip alp_linux_amd64.zip && \
#  install alp /usr/local/bin/alp
FROM nginx:1.10

COPY --from=build-dev /isubata /home/isucon/isubata
#COPY --from=build-dev /isubata/files/app/nginx.conf /etc/nginx/conf.d/isucon.conf
COPY isucon.conf /etc/nginx/conf.d/isucon.conf
