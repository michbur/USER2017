---
title: "AmyloGram: prediction of amyloid sequences in R"
author: |
  | Michał Burdukiewicz^1^, Piotr Sobczyk^2^, Stefan Rödiger^3^, Anna Duda-Madej^4^, Marlena Gąsior-Głogowska^5^, Paweł Mackiewicz^1^ and Małgorzata Kotulska^5^
  |
  | 1. University of Wrocław, Department of Genomics
  | 2. Wrocław University of Science and Technology, Faculty of Pure and Applied Mathematics
  | 3. Brandenburg University of Technology Cottbus-Senftenberg, Institute of Biotechnology
  | 4. Wrocław Medical University, Department of Microbiology
  | 5. Wrocław University of Science and Technology, Faculty of Fundamental Problems of Technology
institute: 
  - $^1$University of Wrocław, Department of Genomics
  - $^2$Wrocław University of Science and Technology, Faculty of Pure and Applied Mathematics
  - $^3$Brandenburg University of Technology Cottbus-Senftenberg, Institute of Biotechnology
  - $^4$Wrocław Medical University, Department of Microbiology
  - $^5$Wrocław University of Science and Technology, Faculty of Fundamental Problems of Technology
output: html_document
bibliography: biogram.bib
---

**Keywords**: Amyloids, n-grams, machine learning, random forest

**Webpages**: https://CRAN.R-project.org/package=AmyloGram, https://github.com/michbur/AmyloGramAnalysis

Amyloids are proteins associated with important clinical disorders (e.g., Alzheimer's or Creutzfeldt-Jakob"s diseases). Despite their great diversity, all amyloid proteins can undergo their aggregation initiated by 6- to 15-residue segments. The aggregation propensity seem to not depend on the exact amino acid residues, but rather on their physicochemical properties. Therefore, we created a model of amyloidogenicity incorporating this knowledge.

We created 524,284 reduced amino acid alphabets based on diversified combinations of the physicochemical properties of amino acid residues. Using very fast implementation of the random forest classifier from the **ranger** package we cross-validated all reduced alphabets and identified one that provided the best discrimination between amyloids and non-amyloids. Our feature selection method found 65 motifs that are the most relevant to the discrimination of amyloid and non-amyloid sequences. 

The reduction of amino acid alphabet turned out very efficient approach because most of the predictors based on them outperformed those trained on the full amino acid alphabet. This result confirmed our assumption on the role of more general amino acid properties in amyloidogenicity. Thanks to the relatively large number of evaluated alphabets, we were able to confirm the significance of amino acid flexibility in the amyloid aggregation. Among 65 most informative amino acid motifs identified during the analysis, 15 were independently confirmed in experimental studies [@lopez_de_la_paz_novo_2002]. The best-performing predictor, **AmyloGram** [@burdukiewicz_prediction_2016], was benchmarked against other tools for amyloid peptides detection using an external dataset. Our software obtained the highest values of performance measures (Area Under the Curve: 0.90, Matthews correlation coefficient: 0.63).

**AmyloGram** was futher used to predict properties of amyloid sequences from the AmyLoad database [@wozniak_amyload:_2015]. We choose 24 hexapeptides which has the opposite annotation and the prediction of **AmyloGram** (12 hexapeptides annoted in the database as amyloidogenic and identified by **AmyloGram** as non-amyloidogenic and 12 hexapeptides annoted in the database as non-amyloidogenic and identified by **AmyloGram** as amyloidogenic). After the experimental validation with Fourier transform infrared spectroscopy we found that 13 peptides have apparently wrong annotation in database, which implies that model of **AmyloGram** is sensitive enough to identify false positives and false negatives in already known data.

Our analysis not only confirmed that amyloidogenicity depends on the general physicochemical properties of proteins, but also revealed which features are the most relevant to the initiation of amyloid aggregation. In addition, our framework identified amyloidogenicity-related amino acid motifs, which were previously confirmed experimentally. The results can be helpful in explaining mechanisms of amyloid aggregation. Aside from creation of the interpretative model of amyloidogenicity, we have also developed an accurate predictor of amyloids, **AmyloGram**.

Despite large computational requirements, the whole study was conducted in *R*, mostly using functions from packages **biogram** and **ranger**. **AmyloGram** itself is distributed as the *R* package and a **shiny** web-server at: www.smorfland.uni.wroc.pl/shiny/AmyloGram/.


# References
