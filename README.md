# Race‑Specific Convolutional Neural Networks for Juvenile Age Prediction

## Project Summary

Estimating age from face images remains a challenging task in computer vision, particularly for younger age groups and across racially diverse populations. Many existing models struggle when only facial images are available and often overlook demographic variability.

This repository presents a method that trains separate Convolutional Neural Networks (CNNs) for different racial groups, aiming to improve age prediction accuracy and fairness for individuals roughly between ages 10 and 25.

## Model Design and Training Setup

The neural network architecture uses a series of convolutional layers that learn meaningful facial features, followed by pooling to reduce spatial noise. These features are then passed through multiple fully connected layers to generate age predictions grouped into 17 bins.

### Training Details

- Epochs: 40  
- Batch Size: 120  
- Learning Rate: 0.001  
- Loss Function: Cross‑Entropy  
- Activation Function: ReLU  

These hyperparameters were tuned during training for optimal performance.

## Datasets

To build a comprehensive dataset, two labeled facial image sources were combined:

### UTKFace

A widely utilized facial image dataset with tens of thousands of images labeled by age, gender, and race. It includes faces spanning from infancy to old age.

### FaceARG

A larger dataset with over 175,000 labeled facial images also annotated by age, gender, and race. This supplemental dataset enhances diversity and population coverage.

### Dataset Preparation

Images from both datasets were curated to improve class balance across racial groups. The merged dataset was refined to emphasize images within the target juvenile age range to support the core goal of accurate young age estimation.

## Results and Discussion

The study conducts a detailed comparison between a model trained on all racial groups together and models trained separately for each race. The findings show that the race‑specific CNNs consistently perform better than the combined model, with higher accuracy and lower error and loss values. Race‑specific models also demonstrate more stable testing accuracy across groups, contributing to fairer outcomes. Although some groups (for example, the Black category) show lower performance, the overall race‑specific approach still surpasses many existing methods. When evaluated using Mean Absolute Error (MAE), the model’s performance is competitive with leading age estimation systems, especially for the 10–25 age range, even though the dataset used is relatively small.


## Summary and Future Work

This project highlights the importance of accounting for demographic differences in facial aging. Traditional one‑size‑fits‑all models tend to ignore meaningful variation across populations, but training models tailored to demographic subgroups can improve fairness and accuracy.

Future extensions could include:
- Incorporating gender and other demographic features
- Exploring more advanced architectures
- Increasing representation for underrepresented groups

This work supports the development of more inclusive and equitable face analysis systems.


## Contributors

This project was part of the U of T Engineering Science course ECE353 (Machine Intelligence, Software & Neural Network), performed by India Tory, Nida Copty, and Thomas Nguyen.
