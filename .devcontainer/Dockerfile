FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

# Install CLI tools
RUN apt-get update && apt-get install -y \
    git \
    curl \
    unzip \
    make \
    python3 \
    python3-pip \
    docker.io \
    && rm -rf /var/lib/apt/lists/*

# Install Terraform
RUN curl -fsSL https://releases.hashicorp.com/terraform/1.9.5/terraform_1.9.5_linux_amd64.zip -o terraform.zip \
    && unzip terraform.zip \
    && mv terraform /usr/local/bin/ \
    && rm terraform.zip

# Install kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" \
    && install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl \
    && rm kubectl

# Install Helm
RUN curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

# Install AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2 awscliv2.zip
