# hash:sha256:66398a984a8fee3f6a5a0a943c55c8c5294d9b88051a0054a1ab09d1b5eb1c16
FROM registry.codeocean.com/codeocean/r-studio:2022.07.0-548-r4.2.1-ubuntu18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        pandoc \
        quarto \
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
    && Rscript -e 'remotes::install_version("quickdag", "0.2.0")' \
    && Rscript -e 'remotes::install_version("rmutil", "1.1.10")' \
    && Rscript -e 'remotes::install_version("tidyr", "1.3.1")'

RUN Rscript -e 'remotes::install_github( \
        "HydeNet", \
        ref = "0.10.11")'
