# Predicting Biomolecular Structure from Language Model attention
### Code from "Predicting RNA structure with Large Language Models: where do we stand?”
###### It is generally shown, and validated in this study, that attention mechanisms in protein Language Models (pLMs) encode evolutionary structural information, facilitating accurate prediction of protein tertiary structure contact maps. Here, we explore whether this concept extends to nucleic acid Language Models (naLMs) for predicting RNA secondary and tertiary structure contact maps. However, our investigation reveals that current language models do not effectively capture structural information. The presented code contains all the trials we performed.


## INSTALLATION

To repeat analysis install and run the Python scripts inside the conda environment:

conda env create -f attentionpred.yml

Usage instructions and installation steps for Miniconda / Anaconda refer to the official web page: https://docs.anaconda.com/free/miniconda/index.html


## EXECUTION

Note: Make sure you change the input / output directories correspondingly!

#### PROTEINS (tertiary structure)

###### Data generation:

1.	All molecules can be sourced from PDB (https://www.rcsb.org/): the ones we used are contained in trRosetta.json
2.	Execute multicontacts.py to generate contact maps (browse inside to change input/target directory and threshold)
3.	Execute del_diag.py to delete nearby contacts (browse inside to change input/target directory and range)

###### Language Model selection:

1.	Execute p_calculation.py (browse inside to change input/target directory and threshold)

###### Structure prediction:

1.	Execute dataload.py for feature extraction
2.	Execute training.py and predict.py for retraining and evaluation

 #### RNA (tertiary structure)

###### Data generation:

1.	Download molecules from PDB: dataset contained in redundants.json (contains dataset after redundancy reduction)
2.	Execute multicontacts_1mer.py or multicontacts_3mer.py to generate contact maps (browse inside to change target directory and cutoff, select script based on LM)
3.	Execute del_diag.py to delete nearby contacts (browse inside to change cutoff)

###### Language Model selection:

1.	Execute p_calculation.py (browse inside to change input/target directory and threshold)

###### Structure prediction:

1.	Execute 1mer_dataload.py or 3mer_dataload.py for feature extraction
2.	Execute training.py and predict.py for retraining and evaluation


#### RNA (secondary structure)

###### Data generation:

1.	Download molecules from PDB: dataset contained in allfordnabert.json or allforrnabert.json (contains dataset after redundancy reduction)

###### Language Model selection:

1.	Execute p_calculation.py (browse inside to change input/target directory and threshold)

###### Structure prediction:

1.	Execute dataload.py for feature extraction
2.	Execute training.py and predict.py for retraining and evaluation
