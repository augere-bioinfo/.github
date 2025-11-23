# Automatic generation of bioinformatics reports

The **augere** framework provides pipelines for automatic generation of Rmarkdown reports for routine bioinformatics analyses.
Each pipeline is represented as an R function that can be called on user-provided data:

```r
library(augere.de)
se <- loadExampleDataset()
res <- runVoom(se, group="dex", comparisons=c("trt", "untrt"))
```

Here, the `runVoom()` call returns the differential expression results from a standard `voom()` analysis,
along with creating an Rmarkdown file that contains all of the **edgeR** and **limma** commands required to reproduce the entire analysis.
This allows users to easily understand what steps were performed and, if necessary, modify the report to customize the analysis.

Currently, we support several common analyses:

- [_augere.de_](https://github.com/augere-bioinfo/augere.de), for differential gene expression with **edgeR** or **limma**.
- [_augere.gsea_](https://github.com/augere-bioinfo/augere.gsea), for gene set enrichment analyses.
- [_augere.screen_](https://github.com/augere-bioinfo/augere.screen), for differential abundance analyses of functional screens.
