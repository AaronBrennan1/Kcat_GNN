# Turnover number predicition of enzymes using Graph Neural Networks



## Overview

This project focuses on predicting the catalytic turnover rate (Kcat) using Graph Neural Networks. This project uses the benchmark dataset from the [TurNup paper](https://www.nature.com/articles/s41467-023-39840-4#data-availability). This work was done as part of a MSc thesis at the University of Galway, which can be read in the [thesis_AaronBrennan.pdf](https://gitlab.com/recon4imd/kinetics/-/blob/dev-aaron/Kcat_prediction/thesis_AaronBrennan_.pdf) file.

## Project Structure

- **Dataset Curation**: In Kcat_dataset_creation.ipynb the data is taken from the original data source, only the important features are kept. Protein and molecular graph strcutures are created from the FASTA and SMILES features respectively.
- **Data Exploration**: Kcat_Data_Analysis.ipynb is used to understand the dataset and visualise some of the features.
- **Model Training and Evaluation**: In the remaining .ipynb files the dataset is converted into a PyTorch Graph Neural Network Model, the models are trained and then evaluated using the R2 metric. Models are trained 10 times and the average test R2 is recorded.

## Results
| Filename | Model                                  | R2 |
|----------|----------------------------------------|------| 
|   *separated_GCN.ipynb       | Protein GCN                            | 0.294|
|    *separated_GAT.ipynb      | Protein GAT                            | 0.297|
|    *separated_GAT.ipynb      | Molecular GAT                          | 0.314|
|  *separated_GCN.ipynb        | Molecular GCN                          | 0.321|
| *combined_GCN.ipynb         | Combined GCN                           | 0.356|
| *combined_GAT.ipynb         | Combined GAT                           | 0.361|
|  *separated_GAT.ipynb        | Protein – Molecular GAT ensemble       | 0.390|
|  *separated_GCN.ipynb         | Protein – Molecular GCN ensemble       | 0.396|
|  *separated_GAT.ipynb        | 3-way Ensemble GAT                     | 0.416|
|  *separated_GCN.ipynb        | 3-way Ensemble GCN                     | 0.419|


## Getting Started

### Google Colab
- I would recommend uploading all these .ipynb files to [Google Colab](https://colab.google/) and running the cells in Colab to not run into prerequisite libraries installation issues and to have access to a GPU for model training and to get quicker inference times on a trained model. 
- To access a GPU in Colab, press the small button beside 'connect'/'connected' in the top right corner. In the Drop-down menu select 'Change runtime type' and then select the GPU option. You will also have to extract the kcat-data.zip and place the folder in home directory of your Google Drive.


