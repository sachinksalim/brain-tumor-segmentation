# Brain Tumor Segmentation using an ensemble of 3D U-Nets

## Team Members
1. Sachin Salim (sachinks@umich.edu)
2. Nowrin Mohamed (nowrin@umich.edu)
3. Shrikant Arvavasu (ashri@umich.edu)

## Abstract
Among brain tumors, gliomas are the most common and aggressive, having extreme variations in shape, size and appearance. Automatic and reliable segmentation methods are important because the large amount of data produced by MRI prevents manual segmentation in a reasonable time. In this paper we aim to develop a deep learning model using a 3D U-Net with adaptations in the preprocessing, training and testing strategies. In addition to this, we created an ensemble of multiple models trained with different hyper-parameters that are used to reduce random errors from each model and yield improved performance. Given the limited computational power, three different 3D U-Net architectures are implemented where each model performs better than the other in its own aspects. Furthermore, the ensemble provides better results.

## Dataset
The datasets used in this study are collected by signing up in synapse.org. The data set was made available for research by the BraTS challenge organizers and contains clinically-acquired preoperative multimodal MRI scans of glioblastoma (GBM/HGG) and low-grade glioma (LGG) containing volumes from multiple institutions. The modalities are:
(i) native (T1)
(ii) post-contrast T1-weighted (T1Gd)
(iii) T2-weighted (T2)
(iv) Fluid Attenuated Inversion Recovery (FLAIR)


| ![Dataset](https://user-images.githubusercontent.com/23056099/208559940-41fcdcf0-81e1-4336-ac86-f8cdc16f1813.png) |
|:--:|
| <b>4 modalities and segmented tumor</b>|

## Model Architecture
| ![model_arch](https://user-images.githubusercontent.com/23056099/208560025-5c35ef6c-6825-4242-815b-724748caea6a.png) |
|:--:|
| <b>3D U-Net Architecture</b>|

We used three different U-Net models with hyperparameters as follows:
Model | N | M | f
--- | --- | --- | --- 
Model1 | 3 | 64 | 64
Model2 | 3 | 96 | 48
Model3 | 4 | 96 | 24

## Results
| ![results](https://user-images.githubusercontent.com/23056099/208560765-d577d4f0-20e9-41d3-9ec1-6a89c63222bb.png) |
|:--:|
| Segmented sub-regions from models 1-3 and the ensemble model is compared with the ground truth for case BraTS2021-00346 |

Performance of the model for the whole tumor (WT) segmentation
Model | Dice Score | Hausdorff Distance
--- | --- | --- 
Model1 | 0.756 | 4.56
Model2 | 0.812 | 4.02
Model3 | 0.804 | 4.33
Ensemble | 0.805 | 3.84
