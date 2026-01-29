# CMP5103 – CNN Performance Under Class Granularity Constraints



This repository contains the complete source code for the CMP5103 course project. The objective of the project is to analyze how **class granularity and dataset complexity** affect convolutional neural network (CNN) performance by comparing multiple architectures on **CIFAR-100** (fine-grained classification) and **CIFAR-10** (coarse-grained classification).



All experiments, evaluations, and visualizations are implemented in a single notebook. The repository is designed to be **fully reproducible**, allowing the project to be evaluated **without retraining models**.



---



#### Project Overview



The project investigates:

\- The effect of fine-grained vs coarse-grained class structure on CNN performance

\- Overfitting behavior under limited per-class samples

\- The impact of architectural complexity and regularization

\- Transfer learning performance using pretrained CNN backbones



The following model categories are included:

\- Custom CNN architectures

\- Regularized CNN variants

\- Transfer learning models (EfficientNet, ResNet)



---



#### Repository Structure



CMP5103project/

    ├── README.md            

    ├── requirements.txt     

    ├── Code/

       └── CMP5103notebook.ipynb

    ├── artifacts/

       └── models/

       └── histories/





#### Directory Description



\- Code/  

     Contains the main project notebook with all experiments, testing, evaluation, and visualizations.



\- artifacts/models/ 

     Contains txt file with the directions of the models weights location under the releases section
the releases link: https://github.com/qatrlnadaalmarzq/CMP5103-project/releases/tag/v1.0-models



\- artifacts/histories/ 

     Contains training history files (`.npy`) used for plotting learning curves and comparisons.



\- requirements.txt

     Lists all Python dependencies required to run the notebook.



---



#### Requirements



All dependencies included in the notebook and listed in `requirements.txt`.



The notebook is compatible with:



* Local Python/Jupyter environments
* Google Colab
* CPU-only execution (for evaluation)
* GPU acceleration (optional, for training)





#### Notebook Configuration



At the top of the notebook, execution mode is controlled by the following variable:

USE_PRETRAINED = True/False



##### Execution Modes



###### Pretrained / Evaluation Mode (USE\_PRETRAINED = True)

* Loads pretrained models and saved training histories
* Skips all training sections
* Runs testing, evaluation, plots, and confusion matrices



###### Full Training Mode (USE\_PRETRAINED = False)

* Trains all models from scratch
* Saves model weights and training histories to artifacts/
* Intended for reproduction or extension of experiments





## How to Run (Evaluation-Only Mode – Recommended)



1. Ensure the following directories exist relative to the repository root: 
   
artifacts/models/

artifacts/histories/

download all the artifacts files including the models weights and histories 
you can Download pretrained .keras weights from the Release link and put them in artifacts/models/.


2. Set at the top of the notebook:

USE_PRETRAINED = True



3. Run the notebook sections in order:

* Notebook Initialization
* Data preprocessing pipeline
* Models Testing
* Models Evaluation



How to Run (Full Training Mode)

1. Set USE_PRETRAINED = False
2. Run All cells



##### Artifact Files



###### CIFAR-100



*Models (under the releases section):*

* model1_cifar100.keras
* model1_cifar100_no_overfitting.keras
* model2_cifar100.keras
* improved_model.keras
* model3.keras
* efficientnetb7_cifar100.keras
* resnet50_cifar100.keras
* resnet50_cifar100_50epochs.keras



*Histories (artifacts/histories/):*

* model1_history.npy
* model1_cifar100_no_overfitting_history.npy
* model2_history.npy
* improved_model_history.npy
* model3_history.npy
* efficientnetb7_cifar100_history.npy
* resnet50_cifar100_history.npy
* resnet50_cifar100_50epochs_history.npy



###### CIFAR-10



*Models (under the releases section):*

* improved_model_cifar10.keras
* model3_cifar10.keras
* efficientnetb7_cifar10.keras
* resnet50_cifar10.keras



*Histories (artifacts/histories/):*

* improved_model_cifar10_history.npy
* model3_cifar10_history.npy
* efficientnetb7_cifar10_history.npy
* resnet50_cifar10_history.npy



If any artifact file is missing, the notebook will print a clear message and skip that model without terminating execution.



#### Reproducibility



* All datasets are loaded using tensorflow datasets
* No absolute or machine-specific paths are used
* Evaluation does not require retraining
* Missing artifacts are handled gracefully
* Results are deterministic given the saved artifacts
















