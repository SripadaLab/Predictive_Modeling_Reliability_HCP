# Predictive Modeling Achieves High Test-Retest Reliability with Resting State Functional Connectivity

### Aman Taxali, Mike Angstadt, Saige Rutherford, Chandra Sripada
#### Department of Psychiatry, University of Michigan, Ann Arbor, MI 

Paper Link: https://www.biorxiv.org/content/10.1101/796714v4

Test-retest reliability is critical for individual differences research. We apply ten predictive modeling methods to resting state connectivity maps from the Human Connectome Project dataset to predict 61 outcome variables. In contrast to reliability of individual resting state connections, we find reliability of the predicted outcomes of predictive models is substantially higher for all ten predictive modeling methods.

### File Descriptions

 * [notebooks](./notebooks)
   * [train_models.ipynb](./notebooks/train_models.ipynb) - Contains the code to train predictive models and save model results (ICC, accuracy, predictions)
   * [visualize_results.ipynb](./notebooks/train_models.ipynb) - Creates visualizations and tables used in the paper, uses saved model results 
 * [saved_models](./saved_models)
   * [cifti/cifti_saved_models.tar.gz](./saved_models/cifti/cifti_saved_models.tar.gz) - tarfile containing outputs of `train_models.ipynb` for grayordinate data
   * [volume/volume_saved_models.tar.gz](./saved_models/volume/volume_saved_models.tar.gz) - tarfile containing outputs of `train_models.ipynb` for volumetric data
   * [edgewise](./saved_models/edgewise) - Directory containing ICC values for raw connectome edges (day1_fc vs day2_fc, not a predictive model)
 * [data](./data)
   * [cifti](./data/cifti) - Grayordinate FC data, used in `train_models.ipynb` to train predictive models
   * [volume](./data/volume) - Volumetric FC data, used in `train_models.ipynb` to train predictive models
   * [folds.pickle](./data/folds.pickle) - Fold indices used for each cross validation step
   * [factors.csv](./data/factors.csv) - General executive and processing speed factors of HCP variables
 * [misc](./misc) - Figures 1, 2 and 3, displayed in readme

### Instructions for Setup
1. Clone this repository on your computer
2. Use the instructions provided in `./data/cifti/readme.txt` and `./data/volume/readme.txt` to download and extract the connectome data
3. Download the unrestricted and restricted HCP behavioral data from http://db.humanconnectome.org and save these csv's in `./data`
4. You can now use `notebooks/train_models.ipynb` to generate predictive modeling results for any one of the following combinations:

   {volume, grayordinate} x {BBS75, BBSCV, Lasso, ... , Random Forest} x {29, 15, 7.5 total scan length} x {.5, .2 FD thresholding}
5. If you're interested in exploring our saved results, extract the tarfiles `cifti/cifti_saved_models.tar.gz` and `volume/volume_saved_models.tar.gz` in the same directories as the tarfiles
6. Use `./notebooks/visualize_results.ipynb` to explore the saved modeling results

### Dependencies

The code provided in this repository was run on the following environment

* python 3.6.6
* numpy 1.17.2
* sciPy 1.3.1
* scikit-learn 0.22.2
* rpy2 2.9.1

---
### Pipeline for calculating test–retest reliability of predicted outcomes

![Figure 1](./misc/figure_1.jpg)

---
### Distribution of test–retest reliabilities for predictive models for volumetric and grayordinate data

![Figure 2](./misc/figure_2.jpg)

---
### Test–retest reliabilities for predicted outcomes across run-lengths and FD thresholds

![Figure 3](./misc/figure_3.jpg)
