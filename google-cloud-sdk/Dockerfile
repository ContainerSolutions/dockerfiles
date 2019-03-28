FROM google/cloud-sdk:236.0.0

# Install Helm
RUN curl https://storage.googleapis.com/kubernetes-helm/helm-v2.13.0-linux-amd64.tar.gz > helm.tar.gz && \
 tar xzvpf helm.tar.gz && \
 cp linux-amd64/helm /usr/local/bin && \
 rm helm.tar.gz && rm -rf linux-amd64

# Install jq
RUN curl -L https://github.com/stedolan/jq/releases/download/jq-1.6/jq-linux64 > /usr/local/bin/jq && \
    chmod +x /usr/local/bin/jq

# Install python3 requests
RUN pip3 install requests

LABEL maintainer="Simone Esposito <simone.esposito@container-solutions.com>"
