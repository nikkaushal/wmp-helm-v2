FROM registry.access.redhat.com/ubi9/ubi:latest

COPY run.sh /
RUN chmod +x /run.sh

RUN dnf install -y unzip jq curl less groff glibc-langpack-en \
    && dnf clean all

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

RUN unzip awscliv2.zip

RUN ./aws/install

RUN rm -rf awscliv2.zip ./aws

ENTRYPOINT ["bash", "/run.sh"]