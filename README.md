# Estimating the accuracy of Moho depth estimates from gravity inversion

**Author: [Aidan Hernaman](https://github.com/AidanHernaman)**

Supervisor: [Leonardo Uieda](https://www.leouieda.com)

## Description

Gravity disturbances are the main source of information with global coverage about depth of the crust-mantle interface (the Moho). But the inverse problem of estimating Moho depth from gravity data is non-unique and requires additional constraints, usually in the form of point estimates from seismology. With these constraints, we are able to estimate the depth to the Moho as well as the density contrast of the anomalous mass distribution. The main sources of uncertainty in the inversion are the uncertainties in the reference models and the poor spatial distribution of constraints, not from the random error in the gravity data. For example, in Africa most seismological data is concentrated along the coast and reference models differ greatly. This makes it particularly challenging to estimate the uncertainty of the estimated Moho depths, since simple error propagation cannot be applied.

In this project, we will investigate the use of cross-validation analysis to estimate the uncertainty in Moho depth estimates from gravity inversion due to the distribution of constraints from seismology. Cross-validation is a statistical method for estimating the prediction accuracy of models on “out-of-sample” data (meaning data that were not used to fit the model). We will use previously published gravity inversion methods and perform cross-validation on the seismological constraints instead of the gravity data. The cross-validation can yield a prediction accuracy for places where constraints are non-existent, providing an insight into the overall uncertainty of the Moho depth model. All modelling and data processing will be done using open-source software and Python programming. Knowledge of Python is not required but minimal programming experience in any language is desirable.

## Notes

- Make sure I've got explanation of cross validation correct.
- Ask for expansion/explanation on why there are disparities between Uieda model and CRUST1.0 model.
- How Haas, 2020 paper uses blocking - seismic regionalization
- Help with code to add legend std and mean in corner of histograms
