---
title: "biogram: n-gram analysis of biological sequences in R"
author: |
   | Piotr Sobczyk^1^, Chris Lauber^2^, Pawel Mackiewicz^3^ and Michal Burdukiewicz^3^
   |
   | 1. Wroclaw University of Science and Technology, Faculty of Pure and Applied Mathematics
   | 2. Technical University of Dresden, Institute for Medical Informatics and Biometry
   | 3. University of Wroclaw, Department of Genomics
institute: 
   - $^1$Wroclaw University of Science and Technology, Faculty of Pure and Applied Mathematics
   - $^2$Technical University of Dresden, Institute for Medical Informatics and Biometry
   - $^3$University of Wroclaw, Department of Genomics
output: html_document
bibliography: biogram.bib
---

**Keywords**: Proteins, n-grams, machine learning, feature selection

**Webpages**: https://CRAN.R-project.org/package=biogram, https://CRAN.R-project.org/package=signalHsmm

n-grams (k-mers) are vectors of *n* characters derived from input sequences. Originally developed for natural language processing, they are also widely used in genomics, transcriptomics and proteomics. Despite the continuous interest in the sequence analysis, there are only a few tools tailored for comparative n-gram studies. Moreover, they often do not contain efficient feature-filtering methods, which severely hampers the application of these methods.

To facilitate comprehensive analysis of n-grams, we created biogram software. Aside from essential  functionalities, like efficient data storage, we also implemented a feature selection method. QuiPT (Quick Permutation Test) uses several filtering criteria such as information gained to choose significant features faster than commonly used feature selection methods. 

n-grams may be used as an extension of a complex stochastic model. Here we implemented n-grams as hidden states in a hidden semi-Markov model of signal peptides called signalHsmm. These N-terminal targeting signals are responsible for targeting of proteins to endomembrane system and their export outside the cell. After reaching the destination, signal peptides are cut off by the signal peptides. n-g

In our model, the cleavage site is modelled by a set of n-grams reflecting variability of this region. This approach not only yields the largest AUC value (AUC = 0.98) in comparison to other software, but also allow more precise prediction of the exact cleavage site. Another advantage of the combined HSMM – n-gram approach is its flexibility. Our model recognises malaria parasites Plasmodium and their relatives  with AUC = 0.92, i.e. more accurately than popular programs (AUC = 0.84).


# References
