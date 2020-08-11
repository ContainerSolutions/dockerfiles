FROM google/cloud-sdk:304.0.0-alpine
ENV KUSTOMIZE_VERSION 3.8.1
RUN gcloud components install kubectl \
 && apk add docker make curl python3 bash \
 && curl -#Lf https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv${KUSTOMIZE_VERSION}/kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz -o kustomize.tar.gz \
 && tar zxf kustomize.tar.gz \
 && mv kustomize /usr/local/bin \
 && chmod +x /usr/local/bin/kustomize \
 && rm kustomize.tar.gz