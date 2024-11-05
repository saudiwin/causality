# README


This repository contains the Quarto files necessary to reproduce
“Holistic Causal Learning with Causal Graphs: A Credible Method for
Study Design and Preregistration in the Social Sciences” by Robert
Kubinec. Please see the file `code/prereg_causal_graph.qmd` for the main
text of the article with embedded calculations of the entropy of causal
graphs. The PDF version of the main article with a doi can be found at:
https://osf.io/preprints/socarxiv/a492b/.

The appendix, which contains additional analyses, can be found in the
document `code/prereg_causal_graph_SI.qmd` in this repository. The
appendix contains additional analyses of the entropy of causal graphs.

## Execution and Runtime

These files can be compiled using Rstudio and Quarto or from the command
line using only Quarto. See instructions for installing Quarto available
here: https://quarto.org/docs/get-started/. To render the files from the
command line, use the following commands from the project root
directory:

    quarto render code/prereg_causal_graph.qmd
    quarto render code/prereg_causal_graph_SI.qmd

From within Rstudio, the file can be executed code chunk by code chunk.
The rendering will produce PDFs. Expected execution time should be no
more than a few minutes at most.

## System Specification

The files were compiled with R 4.4.1 and make use of the following R
packages:

    library(dplyr)
    library(HydeNet)
    library(dagitty)
    library(ggdag)
    library(tidyr)
    library(ggplot2)
    library(ggthemes)
    library(quickdag)
    library(entropy)
    library(network)
    library(ggnetwork)
    library(dagitty)
    library(ggdag)
    library(DiagrammeR)
    library(rmutil)
    library(jmuOutlier)
    library(CausalQueries)

Note that two of these packages, `HydeNet` and `quickdag`, are no longer
available on CRAN. `HydeNet` can be installed with the `remotes` package
(available on CRAN) as follows:

First, install a `HydeNet` dependency from BioConductor as follows:

    if (!require("BiocManager", quietly = TRUE))
        install.packages("BiocManager")

    BiocManager::install("graph")

Then install `Hydenet` with the `remotes` package as follows:

    remotes::install_github("nutterb/HydeNet")

`quickdag` can be installed similarly:

    remotes::install_github("jrgant/quickDAG")

The session info from the most recent compilation of the file is as
follows:

``` r
sessionInfo()
```

    R version 4.4.1 (2024-06-14)
    Platform: aarch64-apple-darwin20
    Running under: macOS 15.0

    Matrix products: default
    BLAS:   /Library/Frameworks/R.framework/Versions/4.4-arm64/Resources/lib/libRblas.0.dylib 
    LAPACK: /Library/Frameworks/R.framework/Versions/4.4-arm64/Resources/lib/libRlapack.dylib;  LAPACK version 3.12.0

    locale:
    [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

    time zone: America/New_York
    tzcode source: internal

    attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base     

    other attached packages:
     [1] CausalQueries_1.1.1 Rcpp_1.0.13         jmuOutlier_2.2     
     [4] rmutil_1.1.10       ggnetwork_0.5.13    network_1.18.2     
     [7] entropy_1.3.1       quickdag_0.2.0      DiagrammeR_1.0.11  
    [10] ggthemes_5.1.0      ggplot2_3.5.1       tidyr_1.3.1        
    [13] ggdag_0.2.13        dagitty_0.3-4       HydeNet_0.10.11    
    [16] nnet_7.3-19         dplyr_1.1.4        

    loaded via a namespace (and not attached):
     [1] gtable_0.3.5         QuickJSR_1.3.1       xfun_0.47           
     [4] htmlwidgets_1.6.4    visNetwork_2.1.2     inline_0.3.19       
     [7] lattice_0.22-6       vctrs_0.6.5          tools_4.4.1         
    [10] generics_0.1.3       parallel_4.4.1       stats4_4.4.1        
    [13] curl_5.2.2           tibble_3.2.1         fansi_1.0.6         
    [16] pkgconfig_2.0.3      checkmate_2.3.2      RColorBrewer_1.1-3  
    [19] dirmult_0.1.3-5      RcppParallel_5.1.9   lifecycle_1.0.4     
    [22] compiler_4.4.1       stringr_1.5.1        munsell_0.5.1       
    [25] codetools_0.2-20     htmltools_0.5.8.1    yaml_2.3.10         
    [28] htmlTable_2.4.3      pillar_1.9.0         MASS_7.3-60.2       
    [31] StanHeaders_2.32.10  boot_1.3-30          rstan_2.32.6        
    [34] tidyselect_1.2.1     digest_0.6.37        stringi_1.8.4       
    [37] purrr_1.0.2          rsvg_2.6.1           latex2exp_0.9.6     
    [40] fastmap_1.2.0        grid_4.4.1           colorspace_2.1-1    
    [43] cli_3.6.3            magrittr_2.0.3       loo_2.8.0           
    [46] messaging_0.1.0      pkgbuild_1.4.4       tidygraph_1.3.1     
    [49] utf8_1.2.4           withr_3.0.1          scales_1.3.0        
    [52] backports_1.5.0      rmarkdown_2.28       matrixStats_1.4.1   
    [55] igraph_2.0.3         gridExtra_2.3        coda_0.19-4.1       
    [58] evaluate_1.0.0       knitr_1.48           V8_5.0.0            
    [61] rstantools_2.4.0     rlang_1.1.4          glue_1.7.0          
    [64] DiagrammeRsvg_0.1    rstudioapi_0.16.0    jsonlite_1.8.8      
    [67] R6_2.5.1             plyr_1.8.9           statnet.common_4.9.0

The file was compiled using Mac OS X Sequoia 15.0 with an M3 chip.
