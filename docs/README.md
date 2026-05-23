---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: eYY-4yp-project-template
title:
---

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

# EEG-Based Stress Detection Using Euclidean And
Hyperbolic Space Deep Learning Techniques

#### Team

- e20078, D.M.N.H Dissanayaka, [email](e20078@ce.pdn.ac.lk)
- e20121, H.P.M.S. Gunasinha, [email](e20121@ce.pdn.ac.lk)
- e20286, K.P.S. Perera, [email](e20286@ce.pdn.ac.lk)

#### Supervisors

-Prof. Roshan Ragel, [email](roshanr@eng.pdn.ac.lk)
-Mr. Nimishan Sivaraj, [email](nimishan@eng.pdn.ac.lk)

#### Table of content

1. [Abstract](#abstract)
2. [Related works](#related-works)
3. [Methodology](#methodology)
4. [Experiment Setup and Implementation](#experiment-setup-and-implementation)
5. [Results and Analysis](#results-and-analysis)
6. [Conclusion](#conclusion)
7. [Publications](#publications)
8. [Links](#links)

---

<!-- 
DELETE THIS SAMPLE before publishing to GitHub Pages !!!
This is a sample image, to show how to add images to your page. To learn more options, please refer [this](https://projects.ce.pdn.ac.lk/docs/faq/how-to-add-an-image/)
![Sample Image](./images/sample.png) 
-->


## Distinguishing between simple physiological arousal
and the maladaptive state of true stress is crucial. This harmful
condition arises when environmental demands exceed an organ
ism’s coping capacity, impairing physiological recovery. Due to
its widespread negative impact, early and accurate detection
of maladaptive stress is vital for protecting personal, social,
and economic wellbeing in today’s fast-paced world. Electroen
cephalography (EEG), as a primary method for monitoring
neural activity, has shown significant promise in identifying
the distinct brain states associated with this stress. Modern
deep learning architectures provide a powerful approach by
automatically extracting meaningful patterns and hierarchical
features from complex EEG data. This comprehensive survey
offers researchers, practitioners, and technology enthusiasts a
definitive overview of current advancements and highlights the
future directions of EEG-based stress detection using deep
learning.

## EEG-based stress detection has been widely studied using both classical machine learning and deep learning techniques. Early approaches relied on handcrafted feature extraction such as spectral power, entropy, and statistical measures, followed by classifiers like Support Vector Machines (SVM), k-Nearest Neighbours (k-NN), and Linear Discriminant Analysis (LDA). These methods achieved reasonable performance in controlled environments but suffered from poor generalization and heavy dependence on manual feature engineering.

With the rise of deep learning, CNN-based models became popular for automatically learning spatial and spectral representations from EEG signals. Recurrent architectures such as LSTM and GRU further improved performance by capturing temporal dependencies in EEG sequences. Hybrid CNN-RNN models demonstrated even stronger results by combining spatial and temporal learning.

More recently, transformer-based models have been applied to EEG analysis, achieving strong performance in long-sequence modeling but requiring large datasets and high computational cost.

A key limitation across most existing work is the assumption of Euclidean geometry. EEG signals inherently exhibit hierarchical and non-linear structures, which are not well represented in flat embedding spaces. This has led to the emergence of hyperbolic neural networks, which better capture hierarchical relationships and improve cross-subject generalization.

## The proposed system is an end-to-end EEG-based stress detection framework built using deep learning and hyperbolic representation learning. The pipeline consists of four main stages:

Data Acquisition
The DEAP dataset is used as the primary benchmark. It contains multi-channel EEG recordings from 32 subjects under controlled emotional stimuli.

Feature Extraction
EEG signals are preprocessed and transformed into two representations:

Time-domain raw EEG signals (32 × 128)
Frequency-domain PSD features (32 × 40 → padded to 32 × 128)

These are fused to form a 2 × 32 × 128 input tensor, combining temporal and spectral information.

Euclidean Feature Learning (CNN)
A CNN (inspired by EEGNet) extracts spatial-temporal features using temporal convolutions, depthwise spatial filtering, and pooling layers.
Hyperbolic Representation Learning
CNN features are projected into Lorentz hyperbolic space, where geometry-aware operations (Lorentz convolution, normalization, pooling) are applied.
Classification
Final classification is performed using Lorentz Multinomial Logistic Regression, which defines decision boundaries in hyperbolic space.

## The model is implemented using deep learning frameworks supporting Euclidean and Riemannian optimization. Training is performed under the following configuration:

Optimizer: Riemannian Adam
Learning rate: 0.001
Batch size: 128
Epochs: 100
Weight decay: 1e-4
Dropout: 0.25
Data type: float32

To handle class imbalance, a combination of WeightedRandomSampler and class-weighted cross-entropy loss is used.

Evaluation is conducted using 5-fold stratified cross-validation. Each fold is trained independently from scratch to ensure fairness. Performance metrics include accuracy, confusion matrix, classification report, and ROC-AUC analysis.

## The proposed model achieves stable and consistent performance across all folds of cross-validation.

Mean validation accuracy: 78.96%
Standard deviation: 0.0268

Training curves show steady convergence of loss, while validation accuracy exhibits minor fluctuations due to EEG variability and resampling effects.

The confusion matrix indicates:

High accuracy in detecting non-stress states
Moderate misclassification in stress class due to class imbalance and inter-subject variability

Overall, the hybrid Euclidean–Hyperbolic architecture improves representation quality compared to traditional Euclidean-only models. Hyperbolic projection enhances the ability to model hierarchical EEG structures, leading to better generalization.

However, performance is still limited by:

Subject variability in EEG signals
Lack of domain adaptation
Dataset size constraints

## This work presents a hybrid EEG-based stress detection system combining deep learning and hyperbolic geometry. By integrating CNN-based feature extraction with Lorentz hyperbolic representation learning, the model effectively captures both spatial-temporal and hierarchical structures in EEG data.

Experimental results demonstrate that the proposed approach achieves competitive performance with a mean accuracy of 78.96%, while maintaining a lightweight and generalizable architecture.

The study highlights the importance of non-Euclidean learning for EEG analysis and shows that hyperbolic embeddings provide a more natural representation for brain signal hierarchies.

Future improvements include subject-independent learning, domain adaptation, and transformer-based hyperbolic architectures for further performance gains.

## Publications
[//]: # "Note: Uncomment each once you uploaded the files to the repository"

<!-- 1. [Semester 7 report](./) -->
<!-- 2. [Semester 7 slides](./) -->
<!-- 3. [Semester 8 report](./) -->
<!-- 4. [Semester 8 slides](./) -->
<!-- 5. Author 1, Author 2 and Author 3 "Research paper title" (2021). [PDF](./). -->


## Links

[//]: # ( NOTE: EDIT THIS LINKS WITH YOUR REPO DETAILS )

- [Project Repository](https://github.com/cepdnaclk/e20-4yp-EEG-Based-Stress-Detection-Using-Euclidean-And-Hyperbolic-Space-Deep-Learning-Techniques)
- [Project Page](https://cepdnaclk.github.io/repository-name)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)

[//]: # "Please refer this to learn more about Markdown syntax"
[//]: # "https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
