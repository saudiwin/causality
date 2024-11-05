# hash:sha256:cbde35536564047b9586d7de98797c569d731fc92c735a7f9133349c9c2ad4a6
FROM registry.codeocean.com/codeocean/py-r:python3.12.4-R4.3.3-JupyterLab4.2.4-RStudiorstudio-server-2024.04.2-764-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        libglpk-dev=5.0-1 \
        libmkl-rt=2020.4.304-2ubuntu3 \
        librsvg2-bin=2.52.5+dfsg-3ubuntu0.2 \
        librsvg2-dev=2.52.5+dfsg-3ubuntu0.2 \
        pandoc=2.9.2.1-3ubuntu2 \
    && rm -rf /var/lib/apt/lists/*

RUN Rscript -e 'remotes::install_version("CausalQueries", "1.1.1")' \
    && Rscript -e 'remotes::install_version("DiagrammeR", "1.0.11")' \
    && Rscript -e 'remotes::install_version("dagitty", "0.3-4")' \
    && Rscript -e 'remotes::install_version("dplyr", "1.1.4")' \
    && Rscript -e 'remotes::install_version("entropy", "1.3.1")' \
    && Rscript -e 'remotes::install_version("ggdag", "0.2.13")' \
    && Rscript -e 'remotes::install_version("ggnetwork", "0.5.13")' \
    && Rscript -e 'remotes::install_version("ggplot2", "3.5.1")' \
    && Rscript -e 'remotes::install_version("ggthemes", "5.1.0")' \
    && Rscript -e 'remotes::install_version("jmuOutlier", "2.2")' \
    && Rscript -e 'remotes::install_version("network", "1.18.2")' \
    && Rscript -e 'remotes::install_version("rmutil", "1.1.10")' \
    && Rscript -e 'remotes::install_version("tidyr", "1.3.1")'

RUN Rscript -e 'remotes::install_github( \
        "jrgant/quickDAG", \
        ref = "6ea3c3baf82d8e1027db0806ac745a4c5b28a927")' \
    && Rscript -e 'remotes::install_github( \
        "nutterb/HydeNet")'

COPY postInstall /
RUN /postInstall
