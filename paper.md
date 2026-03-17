---
title: "fcmtfn: Fuzzy C-Means Clustering for Triangular Fuzzy Numbers in R"
tags:
- R
- fuzzy clustering
- triangular fuzzy numbers
- Likert scale
- linguistic uncertainty
date: "16 March 2026"
output: pdf_document
authors:
- name: José Ortigas
  orcid: "0009-0001-0659-081X"
  affiliation: 1
bibliography: paper.bib
affiliations:
- name: National University of San Marcos, Lima, Peru
  index: 1
---

# Summary

Clustering methods are widely used in empirical research to identify latent
structures in observed data. However, when data are collected through rating
scales, such as Likert-type surveys [@Likert1932], each response category
carries inherent linguistic imprecision: the numerical meaning of a label such
as "satisfied" or "agree" is not universally shared across respondents
[@Krosnick2010]. Classical clustering methods treat these responses as exact
numerical values, thereby ignoring this structural vagueness and potentially
leading to biased results.

The `fcmtfn` R package implements the Fuzzy C-Means algorithm for Fuzzy Data
(FCM-FD), following the general LR framework of @Coppi2012 and the empirical
application of @DUrso2016, extended to Triangular Fuzzy Numbers (TFN) and
building on the classical FCM of @Bezdek1981. It provides a complete and
reproducible workflow for fuzzy clustering of Likert-scale survey data,
including: (1) conversion of Likert responses to TFN using an analyst-defined
dictionary; (2) execution of the FCM-TFN algorithm with adaptive weighting of
centers and spreads; (3) estimation of fuzzy membership degrees for each
respondent across clusters; (4) internal cluster validation via the Xie-Beni
index adapted for fuzzy data [@Xie1991]; and (5) selection of the optimal
number of clusters across a user-defined range.

The analyst defines the TFN dictionary freely, accommodating both symmetric and
asymmetric representations of linguistic imprecision for scales of 5, 7, or 10
points. An example dataset from a real satisfaction survey is included to
illustrate the full workflow. Detailed documentation and vignettes are available
at the package repository: https://github.com/muchillin/fcmtfn.

# Statement of Need

Several R packages provide functionality for fuzzy clustering of crisp data.
Notable examples include `ppclust` [@Cebeci2019], which implements a broad
family of fuzzy and possibilistic clustering algorithms, and `fclust`
[@Ferraro2015], which offers fuzzy k-means and related methods. However, these
packages operate on standard numerical matrices and do not natively handle
*fuzzy-valued data*, i.e., datasets where each observation is itself a fuzzy
number rather than a crisp value.

To the best of our knowledge, no existing R package provides a unified
implementation of FCM for fuzzy data (FCM-FD) in the context of Likert-scale
surveys. The `fcmtfn` package fills this gap by implementing the FCM-FD model
of @Coppi2012 specialized to Triangular Fuzzy Numbers, covering the full
analytical pipeline from raw survey responses to validated cluster solutions.
This makes the methodology accessible to researchers in social sciences,
marketing, tourism, and health sciences who routinely collect data through
Likert-scale instruments and require clustering methods that explicitly account
for linguistic uncertainty.

The package is particularly relevant for analysts who need to: (a) model
response imprecision through asymmetric TFN reflecting non-uniform category
interpretations; (b) obtain fuzzy membership degrees that capture partial
cluster belonging; and (c) determine the optimal number of clusters through a
principled internal validity criterion adapted to the fuzzy data setting.

# Acknowledgements

The author is grateful to the Observatorio Ciudadano Lima Cómo Vamos for
providing access to the survey data included in the package. The author
declares no conflicts of interest. No external funding was received for this
work.

# References
