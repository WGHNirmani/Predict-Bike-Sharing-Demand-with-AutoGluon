# Report: Predict Bike Sharing Demand with AutoGluon Solution

#### Wackwella Gamage Hirunika Nirmani

## Initial Training

### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

When I attempted to submit the initial predictions, everything went smoothly. The submission process was successful without encountering any issues.

### What was the top ranked model that performed?

The top-ranked model that performed was the WeightedEnsemble_L3, achieving a validation score of -53.01.

## Exploratory data analysis and feature creation

### What did the exploratory analysis find and how did you add additional features?

The exploratory analysis revealed a discrepancy in capturing the datetime variable, as it wasn't recognized as a numerical variable in the histogram of the training data. To address this, I engineered three new features - hour, day, and month - extracted from the datetime object to enhance the dataset.

### How much better did your model preform after adding additional features and why do you think that is?

After incorporating the hour, day, and month features, there was a significant enhancement in model performance, with the Kaggle score decreasing from 1.7 to 0.7. This improvement suggests that the additional features provided the model with more nuanced information, enabling it to capture complexities beyond what the initial features could explain.

## Hyper parameter tuning

### How much better did your model preform after trying different hyper parameters?

I experimented with two different hyperparameter configurations. Initially, I extended the training duration and pruned poorly performing models, resulting in an improved model performance and a Kaggle score of 0.4. However, when I introduced additional hyperparameters using hyperparameter_tune_kwargs, including 'num_trials': 3, 'scheduler': 'local', and 'searcher': 'auto', the model's performance decreased, yielding a Kaggle score of 1.4. Upon consulting the documentation, I discovered a recommendation against hyperparameter tuning, which may explain the observed decline in performance.

### If you were given more time with this dataset, where do you think you would spend more time?

Given additional time with this dataset, I would dedicate more effort to feature engineering. It appears to be the only aspect of the workflow that hasn't been fully automated yet.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

| model        | hpo1    | hpo2                          | hpo3    | score |
| ------------ | ------- | ----------------------------- | ------- | ----- |
| initial      | default | default                       | default | 1.8   |
| add_features | default | default                       | default | 0.75  |
| hpo          | default | removed poor performing model | Time    | 0.50  |

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary

This project centered on leveraging AutoGluon to automate machine learning workflows, highlighting the importance of feature engineering and exploratory data analysis (EDA). Throughout the process, the WeightedEnsemble_L3 consistently emerged as the top-performing model.

### Key Takeaways:

~ Automation with AutoGluon: Employing AutoGluon enabled the automation of intricate machine learning tasks, such as hyperparameter tuning and model selection, resulting in significant reductions in manual labor and enhanced workflow efficiency.

~ Feature Importance: Recognizing the significance of feature importance proved instrumental in enhancing model performance. By discerning influential features, we could prioritize feature engineering efforts and optimize model accuracy.

~ Exploratory Data Analysis (EDA): Thorough exploration of the dataset provided valuable insights into underlying patterns, correlations, and relationships among variables. This comprehensive understanding guided feature selection and engineering, facilitating more informed modeling decisions.
