FROM ubuntu:latest

ARG TERRAFORM_VERSION=1.1.7
ARG TERRAGRUNT_VERSION=0.36.6

RUN apt-get update -y && \
    apt-get install wget -y && \
    apt-get install unzip -y && \
    apt-get install vim -y

RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/ && \
    chmod +x /usr/local/bin/terraform

RUN wget https://github.com/gruntwork-io/terragrunt/releases/download/v${TERRAGRUNT_VERSION}/terragrunt_linux_amd64 && \
    mv terragrunt_linux_amd64 /usr/local/bin/terragrunt && \
    chmod +x /usr/local/bin/terragrunt

RUN apt-get install -y python3-pip && \
    pip3 install --upgrade pip && \
    pip3 install awscli --upgrade --user

ENV PATH=~/.local/bin:$PATH
