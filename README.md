# AHTP-DL 
This repository contains the python code and the datasets used to produce the results of the research article titled "Boosted Prediction of Antihypertensive Peptides using Deep Learning". </br> The proposed model was developed on an online paltform "Google Colaboratory" which provides the facility to execute code online on jupyter notebook. </br> This code can also be used by any offline or online platform in Jupyter Notebook by changing the paths in each .ipynb file. </br> In following section some brief information for each file is given. </br> Detailed infromation is also given inside the files.
# Data Sets
allseq.csv

All raw peptide sequences of benchmarking dataset in Fasta format.

fet_all_0.csv

Dipeptide Composition (DPC) features with Gap 0 for benchmarking dataset.

fet_all_1.csv

DPC features with Gap 1 for benchmarking dataset.

fet_all_2.csv

DPC features with Gap 2 for benchmarking dataset.

fet_all_3.csv

DPC features with Gap 3 for benchmarking dataset.

allseq_ind.csv

All raw peptide sequences of independent dataset in Fasta format.

zero_ind.csv

DPC features with Gap 0 for benchmarking dataset.

one_ind.csv

DPC features with Gap 1 for benchmarking dataset.

two_ind.csv

DPC features with Gap 2 for benchmarking dataset.

three_ind.csv

DPC features with Gap 3 for benchmarking dataset.

tes3.txt

Sample raw peptides to test.

# Trained Models 
we have four CNN trained models and one SVM model which is final predictor: 
</br> CNN-weights-bench-cv10-1,2,3-2.hdf5 </br> CNN model trained on benchmarking dataset with features of G-gap Dipeptide with gap (1,2,3) </br> CNN-weights-bench-cv10-0,2,3-2.hdf5 </br> CNN model trained on benchmarking dataset with features of G-gap Dipeptide with gap (0,2,3) </br> CNN-weights-bench-cv10-0,1,3-2.hdf5 </br> CNN model trained on benchmarking dataset with features of G-gap Dipeptide with gap (0,1,3)
</br> CNN-weights-bench-cv10-0,1,2-2.hdf5 </br> CNN model trained on benchmarking dataset with features of G-gap Dipeptide with gap (0,1,2)

# PYTHON CODE
Python code files and their usage is elaborated in this section.

# Data generation
The following steps are used to calculate g-gap dipeptides features for any peptide sequence dataset which is in fasta format. Detailed information about fasta format is also given in file. </br> Steps: </br> 1. Open DPC.ipynb file and run each cell one by one and follow the instructions written in cell. </br> 2. After calculation of DPC features with gap 0,1,2,3 the four files will be generated in the current directory. </br> 3. Open these files one by one and remove first row and first column from each file for further training.

# Training benchmarking dataset
This code is used for training of bechmarking dataset by following steps. </br> 1. perform 3 steps mentioned in data generation section for benchmarking dataset which is in file "allseq.csv " </br> 2. Go to "NC_Training_on_Benchmarking_Dataset.ipynb" file and run each cell one by one and follow the instructions written in cells. </br> As a output there are four CNN models for each of four models there are 10 models (Because we have performed 10-fold Cross Validation) and SVM model (final predictor) and it also have 10 models.
# Testing independent dataset
This code is used for testing on the independent dataset by following steps. </br> 1. perform 3 steps mentioned in data generation section for independent dataset which is in file "allseq_ind.csv" </br> 2. Go to "NC_Testing_on_Independent_Dataset.ipynb" file and run each cell one by one and follow the instructions written in cells.
# Testing any new dataset
This code is used to test the classifier on the new dataset. In Test.ipynb, run each cell one by one and follow the instructions written in cells.
