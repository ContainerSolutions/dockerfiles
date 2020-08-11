FROM google/cloud-sdk:304.0.0-alpine
ENV KUSTOMIZE_VER 3.8.1
RUN gcloud components install kubectl \
 && apk add docker make curl python3 bash \
 && curl -L https://github.com/kubernetes-sigs/kustomize/releases/download/v${KUSTOMIZE_VER}/kustomize_${KUSTOMIZE_VER}_linux_amd64  -o /usr/bin/kustomize \
 && chmod +x /usr/bin/kustomize