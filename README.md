Tests
================
Hélène Polvèche
février, 2022

-   [1 Datas](#datas)
-   [2 Material & Methods](#material--methods)
    -   [2.1 Sources](#sources)
    -   [2.2 Session Info](#session-info)

<img src="./img/fond_presMJ_2.png" style="width:100.0%" />

``` r
library(dplyr)
library(Seurat)
library(ggplot2)
library(RColorBrewer)
library(ggExtra)
library(tidyverse)
```

# 1 Datas

Test 1

# 2 Material & Methods

## 2.1 Sources

-   Test 2
-   Test 3

## 2.2 Session Info

``` r
sessionInfo()
#> R version 4.1.2 (2021-11-01)
#> Platform: x86_64-pc-linux-gnu (64-bit)
#> Running under: Ubuntu 18.04.6 LTS
#> 
#> Matrix products: default
#> BLAS:   /usr/lib/x86_64-linux-gnu/blas/libblas.so.3.7.1
#> LAPACK: /usr/lib/x86_64-linux-gnu/lapack/liblapack.so.3.7.1
#> 
#> locale:
#>  [1] LC_CTYPE=fr_FR.UTF-8       LC_NUMERIC=C              
#>  [3] LC_TIME=fr_FR.UTF-8        LC_COLLATE=fr_FR.UTF-8    
#>  [5] LC_MONETARY=fr_FR.UTF-8    LC_MESSAGES=fr_FR.UTF-8   
#>  [7] LC_PAPER=fr_FR.UTF-8       LC_NAME=C                 
#>  [9] LC_ADDRESS=C               LC_TELEPHONE=C            
#> [11] LC_MEASUREMENT=fr_FR.UTF-8 LC_IDENTIFICATION=C       
#> 
#> attached base packages:
#> [1] stats     graphics  grDevices utils     datasets  methods   base     
#> 
#> other attached packages:
#>  [1] forcats_0.5.1      stringr_1.4.0      purrr_0.3.4        readr_2.1.1       
#>  [5] tidyr_1.1.4        tibble_3.1.6       tidyverse_1.3.1    ggExtra_0.9       
#>  [9] RColorBrewer_1.1-2 ggplot2_3.3.5      SeuratObject_4.0.4 Seurat_4.0.5      
#> [13] dplyr_1.0.7        downloadthis_0.2.1 data.table_1.14.2  DT_0.20           
#> [17] kableExtra_1.3.4   rmdformats_1.0.3  
#> 
#> loaded via a namespace (and not attached):
#>   [1] Rtsne_0.15            colorspace_2.0-2      deldir_1.0-6         
#>   [4] ellipsis_0.3.2        ggridges_0.5.3        fs_1.5.2             
#>   [7] rstudioapi_0.13       spatstat.data_2.1-0   leiden_0.3.9         
#>  [10] listenv_0.8.0         ggrepel_0.9.1         lubridate_1.8.0      
#>  [13] fansi_0.5.0           xml2_1.3.3            codetools_0.2-18     
#>  [16] splines_4.1.2         knitr_1.36            polyclip_1.10-0      
#>  [19] jsonlite_1.7.2        broom_0.7.10          ica_1.0-2            
#>  [22] dbplyr_2.1.1          cluster_2.1.2         png_0.1-7            
#>  [25] uwot_0.1.11           shiny_1.7.1           sctransform_0.3.2    
#>  [28] spatstat.sparse_2.0-0 compiler_4.1.2        httr_1.4.2           
#>  [31] backports_1.4.1       assertthat_0.2.1      Matrix_1.4-0         
#>  [34] fastmap_1.1.0         lazyeval_0.2.2        cli_3.1.0            
#>  [37] later_1.3.0           htmltools_0.5.2       tools_4.1.2          
#>  [40] igraph_1.2.10         gtable_0.3.0          glue_1.5.1           
#>  [43] RANN_2.6.1            reshape2_1.4.4        Rcpp_1.0.7           
#>  [46] scattermore_0.7       cellranger_1.1.0      vctrs_0.3.8          
#>  [49] nlme_3.1-155          svglite_2.0.0         lmtest_0.9-39        
#>  [52] xfun_0.29             globals_0.14.0        rvest_1.0.2          
#>  [55] mime_0.12             miniUI_0.1.1.1        lifecycle_1.0.1      
#>  [58] irlba_2.3.5           goftest_1.2-3         future_1.23.0        
#>  [61] MASS_7.3-55           zoo_1.8-9             scales_1.1.1         
#>  [64] spatstat.core_2.3-2   hms_1.1.1             promises_1.2.0.1     
#>  [67] spatstat.utils_2.3-0  parallel_4.1.2        yaml_2.2.1           
#>  [70] reticulate_1.22       pbapply_1.5-0         gridExtra_2.3        
#>  [73] rpart_4.1.16          stringi_1.7.6         rlang_0.4.12         
#>  [76] pkgconfig_2.0.3       systemfonts_1.0.3     matrixStats_0.61.0   
#>  [79] evaluate_0.14         lattice_0.20-45       ROCR_1.0-11          
#>  [82] tensor_1.5            patchwork_1.1.1       htmlwidgets_1.5.4    
#>  [85] cowplot_1.1.1         tidyselect_1.1.1      parallelly_1.29.0    
#>  [88] RcppAnnoy_0.0.19      plyr_1.8.6            magrittr_2.0.1       
#>  [91] bookdown_0.24         R6_2.5.1              generics_0.1.1       
#>  [94] DBI_1.1.1             haven_2.4.3           withr_2.4.3          
#>  [97] mgcv_1.8-38           pillar_1.6.4          fitdistrplus_1.1-6   
#> [100] survival_3.2-13       abind_1.4-5           future.apply_1.8.1   
#> [103] modelr_0.1.8          crayon_1.4.2          KernSmooth_2.23-20   
#> [106] utf8_1.2.2            spatstat.geom_2.3-1   plotly_4.10.0        
#> [109] tzdb_0.2.0            rmarkdown_2.11        readxl_1.3.1         
#> [112] grid_4.1.2            reprex_2.0.1          digest_0.6.29        
#> [115] webshot_0.5.2         xtable_1.8-4          httpuv_1.6.4         
#> [118] munsell_0.5.0         viridisLite_0.4.0
```
