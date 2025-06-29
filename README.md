# GWAS Project Overview

* This Jupyter notebook was created for my `CS35` final project (Summer 2023) and uses machine learning to analyze genomic data.

---

## Background

* This project began with a focus on Genome Wide Association Studies (`GWAS`), which are used to find associations between genes (genotypes) and particular traits (phenotypes). Datasets like the `1000 Genomes` dataset contain the genetic information for many people and are used to support these studies. 
* However, there is one main complication: each human genome is approximately 3 billion base pairs long, so using the `1000 Genomes` dataset requires handling a lot of data!

---

## GWAS with Hail

In order to work with the `1000 Genomes` dataset, I used the `Hail` library to:

* Access a subset of the dataset through distributed processing  
* Run a `GWAS` (analyze trait associations, generate a Manhattan Plot, etc.)

---

## Quality Control Predictive Modeling

Then, to extend beyond `Hail` tutorials, I shifted my focus to predictive modeling of DNA sample quality (that is, which samples are good quality and which may be unreliable).

* I decided to build a `Random Forest` classifier to predict which DNA samples should be filtered out.

* Also, instead of using all `1000 Genomes`, I decided to build my model using a single person’s genomic data, which contained `10,000` DNA samples.

## Ground Truth + Feature Engineering

* `Hail` provides a built-in filtering method that allows you to identify 'ground truth' DNA sample quality labels (a form of quality control).

* `Hail` also provides a lot of information about each DNA sample, so I decided to use a lot of that ‘messy’ data as my features.

* Then, with the ‘small’ size of 1 genome i.e., `10,000` DNA samples, I could clean the genomic data with `Pandas`/`Numpy` and construct a `Random Forest` classifier.

---
## A Random Forest Success!

* In the end, the `RF` was quite successful (~90% accuracy) at predicting the true quality of the DNA samples (without relying on the `Hail` built-in method itself!).
* We also get to visualize the feature importances, which is always a good idea for Random Forests. : )

---

**Repository URL**: [https://github.com/erikamoore/genomic-predictive-modeling.git](https://github.com/erikamoore/genomic-predictive-modeling.git)