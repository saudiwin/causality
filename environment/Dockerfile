# hash:sha256:a228c407fc412111a9e41c2acb6321a2f14781447d253cc226fa78794d62551f
FROM registry.codeocean.com/codeocean/py-r:python3.12.4-R4.3.3-JupyterLab4.2.4-RStudiorstudio-server-2024.04.2-764-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        libglpk-dev=5.0-1 \
        libmkl-rt=2020.4.304-2ubuntu3 \
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
        "jrgant/quickDAG")' \
    && Rscript -e 'remotes::install_github( \
        "nutterb/HydeNet")'

COPY postInstall /
RUN /postInstall
