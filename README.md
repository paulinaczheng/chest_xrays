# Identifying Chest X-Ray Pathology using Deep Learning 

## Project Motivation
One of the most exciting applications of machine learning, particularly deep learning, is the opportunity to improve medical technology. 

If we are able to automate medical diagnostics, with even better accuracy than currently possible, this could potentially improve:

(1) access to diagnostic services especially in medically underserved populations
(2) health outcomes as conditions are more readily and accurately identified  

## NIH Chest X-Ray Dataset
The publicly available NIH-14 chest x-ray dataset (https://nihcc.app.box.com/v/ChestXray-NIHCC) consists of 112,120 de-identified chest x-ray images and associated data (such as patient sex, and patient age). The dataset's authors labeled the images using natural language processing to text-mine disease classifications from corresponding radiological reports. A random subset of the associated **reports** (not the images, see conclusions below) were independently labeled by two annotators to assess the degree of agreement, with an estimated label accuracy of >90%. 

Due to computer limitations and the size of the images (1024x1024), a random sample of the original dataset was used. This sample consisted of 5,606 images or 5% of the original dataset. 

## Data Exploration

## Data Processing
To facilitate processing, the following was done:

(1) The 1024x1024 images were resized to 128x128. 

(2) Some images were labeled with multiple pathologies (so a single x-ray may be labeled as: nodule, effusion, pneumothorax). In total, 1027 images were diagnosed with multiple pathologies. To facilitate ease of classification and model training, these images were removed from the dataset. 

(3) The original labels were also redefined as: 

0: No Finding
1: Consolidation
2: Infiltration
3: Pneumothorax
4: Effusion
5: Nodule
6: Atelectasis
7: Rare diseases (edema, emphysema, fibrosis, pneumona, pleural thickening, cardiomegaly, hernia)

This resulted in 4,527 128x128 images and their associated labels, which were saved as two arrays.

## Class Imbalance
After visualizing the distribution of pathologies in the cleaned dataset, it was clear that there was class imbalance. 3,044 (~67%) of the data were labeled as no finding. 

To address class imbalance, the following strategies were utilized:

**Multi-Layer Perceptron** 
* Balanced class weights
* Random oversampling

**Convolutional Neural Network**
* Balanced class weights
* Random oversampling
* Data augmentation 

## Multi-Layer Perceptrons (Feed-Forward Neural Network)

## 2D Convolutional Neural Network

## Convergence Issues

## Conclusions
