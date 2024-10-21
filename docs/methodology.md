# Methodology for Well Log Analysis and Facies Classification

## Overview
This project aims to develop a predictive model for well log analysis, specifically targeting facies classification. The challenge involved working with twelve well log datasets, of which only five were labeled, and the remaining seven were unlabeled. Given the limited availability of labeled data, a semi-supervised learning approach was adopted to maximize the utility of the available data and build a robust model that could assist in well log analysis under human supervision.

## Approach
### Initial Model Selection and Training
1. **Data Division**: The available datasets consisted of five labeled well logs and seven unlabeled well logs. Four of the labeled datasets were used for training, while the remaining labeled dataset was used as a universal test set for model evaluation.

2. **Model Testing and Selection**: Initially, multiple machine learning models were tested to identify the most suitable candidate for facies classification. The following models were considered:
   - Support Vector Machine (SVM)
   - AdaBoost
   - Decision Tree
   - Naive Bayes
   - Random Forest
   - Gradient Boosting
   - Neural Network

   After evaluation, the Gradient Boosting model was selected due to its superior performance on the test set.

3. **Optimization**: To further enhance the performance of the selected Gradient Boosting model, several optimization algorithms were applied:
   - **Grid Search**: Exhaustive search over a specified set of hyperparameters.
   - **Randomized Search**: Random sampling of hyperparameter combinations to find the best configuration more efficiently.
   - **Simulated Annealing**: A probabilistic technique to approximate the global optimum of a given function.
   - **Bayes Search**: Bayesian optimization was used to search the hyperparameter space intelligently and converge faster to an optimal solution.

### Semi-Supervised Learning Process
1. **Initial Model Training**: A base model (Model 0) was trained using the four labeled datasets. This model was then tested on the universal test set to establish a baseline accuracy.

2. **Predicting Unlabeled Data**: The trained base model was used to predict the labels of an unlabeled dataset. The newly labeled dataset was added to the training set.

3. **Training with Augmented Data**: A new model was trained using the augmented dataset, which now included both the original labeled data and the newly labeled data. The model's accuracy was carefully monitored to ensure that it did not degrade significantly.

4. **Iterative Process**: This semi-supervised process was repeated for all seven unlabeled datasets. In each iteration, a new model was trained with the expanded dataset, incorporating the labels predicted in the previous step. The goal was to ensure that each newly added dataset contributed positively to the model's overall performance.

## Advantages
- **Efficient Use of Unlabeled Data**: By leveraging semi-supervised learning, the approach maximized the utility of the available unlabeled datasets, thereby improving the model's robustness without requiring extensive manual labeling efforts.
- **Scalable Model Building**: The iterative approach allowed for incremental improvement of the model by progressively adding more data, which contributed to the overall accuracy and stability of the model.
- **Human Supervision**: This approach is designed to work under human supervision, allowing geologists or domain experts to validate the results and adjust the model as needed, thus reducing the risk of incorrect classifications.

