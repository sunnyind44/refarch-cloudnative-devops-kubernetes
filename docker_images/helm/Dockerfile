FROM alpine

ENV HELM_LATEST_VERSION="v2.3.1"

RUN apk add --update ca-certificates \
 && apk add --update -t deps wget \
 && apk add --update bash \
 && wget http://storage.googleapis.com/kubernetes-helm/helm-${HELM_LATEST_VERSION}-linux-amd64.tar.gz \
 && tar -xvf helm-${HELM_LATEST_VERSION}-linux-amd64.tar.gz \
 && mv linux-amd64/helm /usr/local/bin \
 && apk del --purge deps \
 && rm /var/cache/apk/* \
 && rm -f /helm-${HELM_LATEST_VERSION}-linux-amd64.tar.gz

ADD https://github.com/mikefarah/yaml/releases/download/1.8/yaml_linux_amd64 /usr/local/bin/yaml
RUN chmod a+x /usr/local/bin/yaml