FROM google/cloud-sdk:246.0.0

# Install Helm
RUN curl https://storage.googleapis.com/kubernetes-helm/helm-v2.13.0-linux-amd64.tar.gz > helm.tar.gz && \
 tar xzvpf helm.tar.gz && \
 cp linux-amd64/helm /usr/local/bin && \
 rm helm.tar.gz && rm -rf linux-amd64

# Install jq
RUN curl -L https://github.com/stedolan/jq/releases/download/jq-1.6/jq-linux64 > /usr/local/bin/jq && \
    chmod +x /usr/local/bin/jq

# Install python3 requests
RUN apt-get update && \
    apt-get -y install --no-install-recommends python3-pip && \
    rm -rf /var/lib/apt/lists/* && \
    pip3 install requests

# Install kustomize
RUN curl -L https://github.com/kubernetes-sigs/kustomize/releases/download/v2.0.3/kustomize_2.0.3_linux_amd64 > /usr/local/bin/kustomize && \
    chmod +x /usr/local/bin/kustomize

# Install cft
RUN apt-get update && apt-get -y install --no-install-recommends make && \
    rm -rf /var/lib/apt/lists/* && \
    git clone https://github.com/GoogleCloudPlatform/deploymentmanager-samples && \
    cd deploymentmanager-samples/community/cloud-foundation && \
    make prerequisites && \
    make build && \
    make install && \
    cd / && \
    rm -rf deploymentmanager-samples/

# Install mozilla/sops
RUN curl -L https://github.com/mozilla/sops/releases/download/3.3.0/sops-3.3.0.linux > /usr/local/bin/sops && \
    chmod +x /usr/local/bin/sops

LABEL maintainer="Simone Esposito <simone.esposito@container-solutions.com>"
