FROM registry.access.redhat.com/ubi9/ubi:latest

COPY run.sh /
RUN chmod +x /run.sh

RUN dnf install -y unzip jq curl \
    && curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2.zip ./aws \
    && dnf remove -y unzip \
    && dnf clean all

ENTRYPOINT ["bash", "/run.sh"]