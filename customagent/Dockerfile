FROM cloudbees/cbflow-agent:2023.04.0.162443_3.2.41_20230407

USER root
RUN rpm --import https://packages.microsoft.com/keys/microsoft.asc
RUN printf '[azure-cli]\nname="Azure CLI"\nbaseurl=https://packages.microsoft.com/yumrepos/azure-cli\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc' > /etc/yum.repos.d/azure-cli.repo
RUN dnf -y update && dnf -y install git azure-cli
ENV PATH="${PATH}:/root/.azure/cliextensions:/root/.azure/cliextensions/bin"
USER cbflow