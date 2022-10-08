FROM node:lts-alpine3.15
LABEL maintainer="saker.alexandre@gmail.com"

ARG TF_VERSION=1.0.11-r2
ARG GCPCLI_VERSION=405.0.0
ARG TFDOCS_VERSION=0.16.0
ARG TFSEC_VERSION=1.28.0

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN apk upgrade && apk update && apk add --no-cache \
    sudo \
    bash \
    git  \
    zip \
    python3-dev \
    py3-pip  \
    gcc \
    musl-dev \
    libffi-dev \
    openssl \ 
    cargo \
    make \
    curl

# Add Terraform
RUN apk add --no-cache  terraform=$TF_VERSION 

# Add GCP CLi 
RUN curl -sLo gcpcli.tar.gz https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-${GCPCLI_VERSION}-linux-x86_64.tar.gz \
    && tar -xzf gcpcli.tar.gz \
    && ./google-cloud-sdk/install.sh \
    && rm gcpcli.tar.gz 

# Add Terraform Docs
RUN curl -sLo ./terraform-docs.tar.gz https://github.com/terraform-docs/terraform-docs/releases/download/v${TFDOCS_VERSION}/terraform-docs-v${TFDOCS_VERSION}-$(uname)-amd64.tar.gz \
    && tar -xzf terraform-docs.tar.gz \
    && chmod +x terraform-docs \
    && rm terraform-docs.tar.gz \
    && mv terraform-docs /usr/local/bin/terraform-docs

# Add Tfsec
RUN curl -sLo tfsec.tar.gz https://github.com/aquasecurity/tfsec/releases/download/v${TFSEC_VERSION}/tfsec_${TFSEC_VERSION}_linux_amd64.tar.gz \
    && tar -xzf tfsec.tar.gz \
    && mv tfsec /usr/local/bin/tfsec \
    && rm tfsec* 

# Add new user with sudo rights
RUN adduser -D $USERNAME \
    && echo "$USERNAME ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME