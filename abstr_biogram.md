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

To facilitate comprehensive analysis of n-grams, we created **biogram** package. Aside from essential  functionalities, like efficient data storage, we also implemented a novel feature selection method. Commonly permutation tests are used for filtering important n-grams to find if an occurrence of n-gram and a value of a target are independent. However, exhaustive testing of permutations is computationally expensive and, as 
a result, they often become one of the most limiting factors in these kinds of analyses. Therefore, we developed the Quick Permutation Test (QuiPT) which effectively filters n-gram features, without requiring exhaustive testing. It uses several filtering criteria such as information gained to choose the most discriminating features. 

Several studies have highlighted that three-dimensional protein structure depends not only on the exact sequence of amino acids but also on their general physicochemical properties. Therefore, a reduced amino acid alphabet which represents certain subgroups of amino acids, can still retain the information about the protein folding [@murphy_simplified_2000]. Since the function of proteins often depends on their structure, reduced alphabets can be used in prediction of protein roles. The reduction of the alphabet has twofold benefits: reduces the number of possible input variables (n-grams) streamlining development of the model and allow extraction of more straightforward decision rules. 

The generation of reduced amino acid alphabet is facilited through implemented genetic algorithm [@lenckowski_simplifying_2007]. It was modified to work faster and produce more adequate reduced alphabets. We also added distance measures for comparison of reducing alphabet, including similiarity index [@stephenson_unearthing_2013] and our own encoding distance. 

We showcase the n-gram analysis in the problem of signal peptide prediction. Signal peptides are short subsequences present at the N-terminal of proteins. They serve a role similar to the postal code directing proteins to the endomembrane system and in consequence facilitating their export outside the cell. Here we implemented n-grams as hidden states in a hidden semi-Markov model (HSMM) of signal peptides called signalHsmm. This approach yields the largest AUC value (AUC = 0.98) in comparison to other software (signalP 4.0 [@petersen_signalp_2011], signalP 3.0, Phobius, Philius, PrediSi). Another advantage of the n-gram approach is universality of decision rules. Malaria-causing parasites from Plasmodium genus have slightly different amino acid composition of proteins than other organisms, which hinders prediction of their signal peptides in all models using the full amino acid alphabet. The usage of a reduced amino acid alphabet allows signalHsmm to employ universal decision rules, appropriate for proteins belonging to both malaria parasites and other organisms. Thanks to that signalHsmm recognizes signal peptides of malaria parasites with AUC = 0.92, i.e. more accurately than other programs that cannot exceed AUC equal to 0.84.


# References
