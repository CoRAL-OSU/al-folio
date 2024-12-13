---
layout: page
title: Decentralized Bayesian Learning
organization: NSF EPCN
year: 2023
importance: 1
---

Recent technological advances in data acquisition and computation have enabled massive data collection with lower costs, e.g., from Internet-of-Things and smart devices. Consequently, datasets for system modeling and learning are becoming more and more distributed.  Data-driven models aggregating information from distributed datasets provide unrivaled capabilities in prediction and decision making over models learned from individual datasets. However, centralized processing of distributed datasets requires transferring all the raw data to a central entity, incurring concerns on communication bandwidth, privacy, and single point of failure.

Without taking into account epistemic uncertainties, models learned by decentralized optimization of a point estimate, such as maximum likelihood and maximum a posteriori, are likely to suffer from poor generalization and overconfident decisions, particularly when the training data is noisy and insufficient for large-scale models. Bayesian learning provides a principled, rigorous framework to process noisy datasets and create uncertainty-aware models for robust decisions and predictions. Bayesian learning employs Bayes' law to compute or approximate the posterior distribution of unknown model parameters from a prior distribution of the parameters and a data likelihood function. It is a natural approach to quantify uncertainty and learn efficiently without overfitting. Bayesian learning makes explicit use of prior information, which is often used implicitly as regularization in optimization. 
This project aims to create a theoretical framework for designing and analyzing **decentralized Bayesian learning** algorithms via gradient-based MCMC and to identify feasible protocols for enhancing communication and computational efficiency of the algorithms and their privacy properties.
**Relevant Publications**

<div class="publications">


{% bibliography --file DBL %}


</div>
