---
title: "Integrated analysis of digital PCR experiments in R"
author: |
  |  Michał Burdukiewicz^1^, Jim Huggett^2^, Alexandra Whale^2^, Piotr Sobczyk^3^, Paweł Mackiewicz^1^, Andrej-Nikolai Spiessk^4^, Peter Schierack^5^ and Stefan Reodiger^5^
  |
  | 1. University of Wrocław, Department of Genomics
  | 2. LGC, Molecular and Cell Biology Team
  | 3. Wrocław University of Science and Technology, Faculty of Pure and Applied Mathematics
  | 4. University Medical Center Hamburg-Eppendorf
  | 5. Brandenburg University of Technology Cottbus-Senftenberg, Institute of Biotechnology
institute: 
  - $^1$University of Wrocław, Department of Genomics
  - $^1$LGC, Molecular and Cell Biology Team
  - $^3$Wrocław University of Science and Technology, Faculty of Pure and Applied Mathematics
  - $^4$University Medical Center Hamburg-Eppendorf
  - $^5$Brandenburg University of Technology Cottbus-Senftenberg
output: html_document
bibliography: dpcr.bib
---
  
**Keywords**: digital PCR, multiple comparison, GUI, reproducible research

**Webpages**: https://CRAN.R-project.org/package=dpcR, http://michbur.github.io/dpcR_manual/, http://michbur.github.io/pcRuniveRsum/

Digital PCR (dPCR) is a variant of PCR, where the PCR amplification is conducted in multiple small volume reactions (termed partitions) instead of a bulk. The dichotomous status of each partition (positive or  negative amplification) is used for absolute quantification of the template molecules by Poisson transformation of the proportion of positive partitions. The vast expansion of dPCR technology and its applications has been followed by the development of statistical data analysis methods. Yet, the software landscape is scattered, consisting of scripts in various programming languages, web servers with narrow scopes or closed source vendor software packages, that are usually tightly tied to their platform. This leads to unfavourable environments, as results from different platforms, or even from different laboratories using the same platform, cannot be easily compared with one another.

To address these challenges, we developed the dpcReport shiny server that provides an open-source tool for the analysis of dPCR data. dpcReport provides a streamlined analysis framework to the dPCR community that is compatible with the data output (e.g., CSV, XLSX) from different dPCR platforms (e.g., Bio-Rad QX100/200, Biomark). This goes beyond the basic dPCR data analysis with vendor-supplied softwares, which is often limited to the computation of the mean template copy number per partition and its uncertainty. dpcReport gives users more control over their data analysis and they benefit from standardization and reproducible analysis.

Our web server analyses data regardless of the platform vendor or type (droplet or chamber dPCR). It is not limited to the commercially available platforms and can also be used with experimental systems by importing data through the universal REDF format, which follows the IETF RFC 4180 standard. dpcReport provides users with advanced tools for data quality control and it incorporates statistical tests for comparing multiple reactions in an experiment [@burdukiewicz_methods_2016], currently absent in many dPCR-related software tools. dpcReport provides users with advanced tools for data quality control. The conducted analyses are fully integrated within extensive and customizable interactive HTML reports including figures, tables and calculations. 

To improve reproducibility and transparency, a report may include snippets in *R* enabling an exact reproduction of the analysis performed by dpcReport. We developed **dpcR** package to collect all functionalities employed by the shiny server. Furthermore, the package provides additional functions facilitating analysis and quality control of dPCR data. Nevertheless, core functionalities are available through the shiny server to minimize entry barrier required to use our software.

Both dpcReport and *dpcR* follow the standardized dPCR nomenclature of the dMIQE guidelines [@huggett_digital_2013]. Since the vast functionality offered by our software may be overwhelming at first, our software is extensively documented. The documentation is enriched by the analysis of sample data sets.

The dpcReport web server and **dpcR** package belong to [pcRuniveRsum](http://michbur.github.io/pcRuniveRsum/), a collection of *R* tools for analysis DNA Amplification of Experiments

# References
