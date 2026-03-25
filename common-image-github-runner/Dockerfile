FROM amazonlinux:2

RUN yum update -y && \
    yum install -y \
    git curl tar gzip unzip which sudo shadow-utils \
    libicu openssl-libs krb5-libs zlib libstdc++ && \
    amazon-linux-extras install docker -y || yum install -y docker

WORKDIR /actions-runner

RUN curl -o actions-runner.tar.gz -L \
https://github.com/actions/runner/releases/latest/download/actions-runner-linux-x64.tar.gz && \
    tar xzf actions-runner.tar.gz && \
    rm -f actions-runner.tar.gz

CMD ["./run.sh"]