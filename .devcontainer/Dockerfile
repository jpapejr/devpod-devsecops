FROM --platform=linux/amd64 mcr.microsoft.com/devcontainers/python:0-3.11

ENV TERRAFORM_VERSION=1.6.0

RUN apt update -y && \
     DEBIAN_FRONTEND=noninteractive TZ="America/New_York" apt install -y --no-install-recommends bash curl git ca-certificates snapd && \
     apt upgrade openssl file -y 
     
RUN curl -O https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
     unzip -o terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
     rm -f terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
     chmod +x terraform && \
     cp ./terraform /usr/local/bin/terraform


RUN echo 'export PS1="\[\e[34m\]IBM\[\e[m\]☁️  # "' > /root/.bashrc
RUN echo 'export PATH="$PATH:/root/bin"' >> /root/.bashrc


ENTRYPOINT ["bash"]
