# Results Summary for Well Log Analysis and Facies Classification

## Table 1: Comparing Optimization Algorithms for Classification on Well Log Data
This table provides an overview of the performance metrics for various machine learning models applied to the well log data, comparing metrics such as Area Under the Curve (AUC), Classification Accuracy (CA), and efficiency.

| Model              | Train Time (sec) | Test Time (sec) | AUC  | CA   | F1   | Precision | Recall | MCC  | Specificity | LogLoss |
|--------------------|-----------------|----------------|------|------|------|-----------|--------|------|-------------|---------|
| SVM                | 9.936           | 1.178          | 0.884| 0.563| 0.592| 0.697     | 0.563  | 0.405| 0.866       | 0.877   |
| AdaBoost           | 0.571           | 0.068          | 0.928| 0.911| 0.911| 0.911     | 0.911  | 0.853| 0.952       | 3.085   |
| Decision Tree      | 3.753           | 0.018          | 0.929| 0.919| 0.918| 0.918     | 0.919  | 0.865| 0.939       | 1.482   |
| Naive Bayes        | 0.466           | 0.093          | 0.952| 0.790| 0.798| 0.813     | 0.790  | 0.671| 0.908       | 0.576   |
| Random Forest      | 9.764           | 1.351          | 0.965| 0.860| 0.848| 0.860     | 0.860  | 0.761| 0.843       | 0.543   |
| Gradient Boosting  | 5435.263        | 3.481          | 0.991| 0.938| 0.937| 0.938     | 0.938  | 0.896| 0.947       | 0.217   |
| Neural Network     | 107.059         | 0.140          | 0.970| 0.863| 0.860| 0.861     | 0.863  | 0.769| 0.902       | 0.371   |

- **Gradient Boosting** provided the highest AUC (0.991) and accuracy (93.8%), demonstrating strong predictive power but required the longest training time (5435.263 sec). This makes it the most computationally expensive model.
- **Naive Bayes** was quick to train and showed a relatively high AUC (0.952), but its classification accuracy (CA) was lower (79.0%), suggesting it might not be suitable for detailed analysis without further tuning.
- **Decision Tree** and **Random Forest** showed good performance with balanced training time and high classification metrics, but **Gradient Boosting** outperformed them in AUC and accuracy.


## Table 2: Iterative Semi-Supervised Learning Process for Well Log Classification
This table presents the iterative learning process used to label the unlabeled well logs using a combination of the initial labeled datasets and the new data predictions.

| Iteration | Training Set Name | No. of Training Instances | Validation Set Name | No. of Validation Instances | Prediction Set Name | Prediction Instances | New Training Set Name | New Training Set Instances | Accuracy Before | Accuracy After | AUC Before | AUC After |
|-----------|-------------------|--------------------------|---------------------|---------------------------|---------------------|----------------------|-----------------------|---------------------------|----------------|---------------|------------|-----------|
| 0         | Combined 4        | 2991                     | Well 5              | 692                       | NA                  | 0                    | Combined 4            | 2991                      | 93.64%         | 93.64%        | 98.81%     | 98.81%    |
| 1         | Combined 4        | 2991                     | Well 5              | 692                       | Well 6              | 1306                 | Combined 5            | 4297                      | 93.64%         | 92.63%        | 98.81%     | 98.70%    |
| 2         | Combined 5        | 4297                     | Well 5              | 692                       | Well 7              | 774                  | Combined 6            | 5071                      | 92.48%         | 92.63%        | 98.68%     | 98.76%    |
| 3         | Combined 6        | 5071                     | Well 5              | 692                       | Well 8              | 759                  | Combined 7            | 5830                      | 92.77%         | 92.48%        | 98.76%     | 98.80%    |
| 4         | Combined 7        | 5830                     | Well 5              | 692                       | Well 9              | 722                  | Combined 8            | 6552                      | 92.63%         | 92.91%        | 98.79%     | 98.80%    |
| 5         | Combined 8        | 6552                     | Well 5              | 692                       | Well 10             | 550                  | Combined 9            | 7102                      | 92.63%         | 92.48%        | 98.80%     | 98.67%    |
| 6         | Combined 9        | 7102                     | Well 5              | 692                       | Well 11             | 500                  | Combined 10           | 7602                      | 92.63%         | 92.19%        | 98.66%     | 98.75%    |
| 7         | Combined 10       | 7602                     | Well 5              | 692                       | Well 12             | 320                  | Combined 11           | 7922                      | 92.19%         | 92.19%        | 98.74%     | 98.72%    |

- **Accuracy and AUC Stability**: The accuracy before and after adding each new dataset showed slight fluctuations, but overall, the model's performance remained stable, indicating that the semi-supervised learning approach was effective.
- **Iteration 3 and 4** showed slight increases in both accuracy and AUC, which suggests that the newly predicted labels were generally beneficial for the model.


## Table 3: Performance Comparison of Optimization Algorithms on Well Log Classification
This table highlights the performance of different optimization algorithms (Grid Search, Randomized Search, Simulated Annealing, Bayes Search) used to optimize the Gradient Boosting model for well log classification.

| Algorithm Name       | Time (sec) | AUC    | CA    | F1    | Precision | Recall | MCC   | Spec  | LogLoss |
|----------------------|------------|--------|-------|-------|-----------|--------|-------|-------|---------|
| Grid Search          | 1517.7     | 0.9855 | 94.78 | 0.9462| 0.9476    | 0.9489 | 0.9053| 0.9969| 0.2816  |
| Randomized Search    | 2784.9     | 0.9928 | 95.98 | 0.9591| 0.9595    | 0.9586 | 0.9273| 0.9975| 0.1692  |
| Simulated Annealing  | 1768.5     | 0.9964 | 96.79 | 0.9675| 0.9676    | 0.9679 | 0.9422| 0.9982| 0.1197  |
| Bayes Search         | 3415.7     | 0.9918 | 95.32 | 0.9522| 0.9526    | 0.9547 | 0.9153| 0.9975| 0.2048  |

- **Simulated Annealing** achieved the best AUC (0.9964) and classification accuracy (96.79%), demonstrating its effectiveness in finding an optimal solution for the problem.
- **Grid Search** took less time compared to Randomized Search and Bayes Search but had a lower AUC (0.9855), indicating it may not be as effective in finding the best hyperparameter combinations.
- **Randomized Search** and **Bayes Search** both showed good performance, but **Simulated Annealing** provided the best trade-off between computational cost and model performance.

