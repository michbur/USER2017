---
  title: "Integrated analysis of digital PCR experiments in R"
author: |
  |  Michal Burdukiewicz^1^, Jim Huggett^2^, Alexandra Whale^2^, Piotr Sobczyk^3^, Pawel Mackiewicz^1^, Andrej-Nikolai Spiessk^4^, Peter Schierack^5^ and Stefan Roediger^5^
  |
  | 1. University of Wroclaw, Department of Genomics
  | 2. LGC, Molecular and Cell Biology Team
  | 3. Wroclaw University of Science and Technology, Faculty of Pure and Applied Mathematics
  | 4. University Medical Center Hamburg-Eppendorf
  | 5. Brandenburg University of Technology Cottbus-Senftenberg, Institute of Biotechnology
institute: 
  - $^1$University of Wroclaw, Department of Genomics
  - $^1$LGC, Molecular and Cell Biology Team
  - $^3$Wroclaw University of Science and Technology, Faculty of Pure and Applied Mathematics
  - $^4$University Medical Center Hamburg-Eppendorf
  - $^5$Brandenburg University of Technology Cottbus-Senftenberg
output: html_document
bibliography: biogram.bib
---
  
**Keywords**: digital PCR, multiple comparison, GUI, reproducible research

**Webpages**: https://CRAN.R-project.org/package=dpcR

Digital PCR (dPCR) is a variant of PCR, where the PCR amplification is conducted in multiple small volume reactions (termed partitions) instead of a bulk. The dichotomous status of each partition (positive or  negative amplification) is used for absolute quantification of the template molecules by Poisson transformation of the proportion of positive partitions. The vast expansion of dPCR technology and its applications has been followed by the development of statistical data analysis methods. Yet, the software landscape is scattered, consisting of scripts in various programming languages, web servers with narrow scopes or closed source vendor software packages, that are usually tightly tied to their platform. This leads to unfavourable environments, as results from different platforms, or even from different laboratories using the same platform, cannot be easily compared with one another.
To address these problems, we developed the dpcReport web server that provides an open-source tool for the analysis of dPCR data. dpcReport provides a streamlined analysis framework to the dPCR community that is compatible with the data output (e.g., CSV, XLSX) from different dPCR platforms (e.g., Bio-Rad QX100/200, Biomark). This goes beyond the basic dPCR data analysis with vendor-supplied softwares, which is often limited to the computation of the mean template copy number per partition and its uncertainty. dpcReport gives users more control over their data analysis and they benefit from standardization and reproducible analysis.
Our web server analyses data regardless of the platform vendor or type (droplet or chamber dPCR). It is not limited to the commercially available platforms and can also be used with experimental systems by importing data through the universal REDF format, which follows the IETF® RFC 4180 standard. dpcReport provides users with advanced tools for data quality control and it incorporates statistical tests for comparing multiple reactions in an experiment [1], currently absent in many dPCR-related software tools. dpcReport provides users with advanced tools for data quality control. The conducted analyses are fully integrated within extensive and customizable interactive HTML reports including figures, tables and calculations. To improve reproducibility and transparency, a report may include snippets in the programming language R enabling an exact reproduction of the analysis performed by dpcReport through functions from the dpcR package [2]. Our software follows the standardized dPCR nomenclature of the dMIQE guidelines [3]. Since the vast functionality offered by dpcReport may be overwhelming at first, our web server is extensively documented. 
Our versatile open source tool for reproducible dPCR data analysis, dpcReport, is available since August 2015. It was tested on eight dPCR data sets obtained from two types of machines produced by two different vendors and tested by approximately four unique users outside of the authors’ group.



# References
