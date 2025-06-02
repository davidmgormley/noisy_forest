# noisy_forest

1) Project Summary
This project evaluates Noisy Forest: a random forest variant that injects noise to encourage diverse tree-fitting on tabular regression datasets. We benchmark Noisy Forest against Random Forest on a curated collection of datasets from PMLB and OpenML, using a fixed train/test split and reproducible pipelines.


2. Dataset Information
- Dataset Criteria
      - I evaluated the models on regression datasets that are less than 10,000 observations
      - I defined this criteria because I found that my model performed particularly well on datasets less than 10,000 observations while experimenting with the OpenML-CTR23 datasets. This threshold was defined prior to the creation of training and holdout datasets from the Penn Machine Learning Benchmarks (see script from commit 2aca6cfbdc79e5f6277b1f223657b15ac9601301).
  
      - Any findings can only be generalized to regression datasets with less than 10,000 observations.
  
- Training datasets and test datasets
      - First, I tuned the Noisy Forest hyperparameters on the OpenML-CTR23 datasets (https://www.openml.org/search?type=study&sort=tasks_included&study_type=task&id=353).
              - Located in datasets/train_datasets_openml-CTR_23
              - Note that these datasets were committed to github after the training and holdout datasets were defined (step below) but before evaluation on the holdout datasets. 
      - Next, I wrote a script (sampling_train_vs_test_datasets_from_pmlb.ipynb) to create a set of train datasets and a set of holdout datasets from Penn Machine Learning Benchmarks (PMLB)(https://epistasislab.github.io/pmlb/). These datasets needed to fit the criteria defined above and also needed to not include any datasets from the OpenML-CTR23 datasets that the model had previously seen.
              - train datasets located in datasets/train_datasets_pmlb.txt
              - holdout datasets located in datasets/holdout_datasets.txt
      - Next, I evaluated my model on the set of training datasets from PMLB and committed the final train/test splits for training data and the final hyperparameter grids to github
      - Lastly, I will evaluate my model on the holdout datasets and report my findings. The model never saw these holdout sets during the training process. 


  

