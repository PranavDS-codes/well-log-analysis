# Well Log Analysis and Facies Classification Project

## Overview
This project implements a semi-supervised learning approach for well log analysis aimed at facies classification. Utilizing well log data, the project focuses on developing a predictive model that classifies geological facies under human supervision. Given that only 5 out of the 12 datasets were labeled, a semi-supervised approach was adopted to make effective use of both labeled and unlabeled data, ensuring robust model performance.

## Repository Structure
```
well-log-analysis/
|
├── README.md                     # Overview of the project
├── requirements.txt              # Dependencies for the project
├── notebooks/
│    ├── initial-modelling/
│    │    ├── initial_raw_modelling.ipynb		# initial modelling for best performing model selection 
│    │    ├── optimizing_initial_model.ipynb  # optimization on the model for best results
│    ├── iterative-modelling/     # Jupyter notebooks for iterative training of the model
│    │    ├── iter1.ipynb
│    │    ├── iter2.ipynb
│    │    ├── iter3.ipynb
│    │    ├── iter4.ipynb
│    │    ├── iter5.ipynb
│    │    ├── iter6.ipynb
│    │    ├── iter7.ipynb
└── docs/
     ├── methodology.md           # Detailed explanation of the methodology
     ├── results_summary.md       # Summary of the model results and findings
```

## Installation
To set up the project locally, follow these steps:

1. **Clone the repository**:
   ```sh
   git clone https://github.com/your_username/Confidential_Project_Repository.git
   cd Confidential_Project_Repository
   ```

2. **Install dependencies**:
   It is recommended to create a virtual environment and install the required dependencies:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```

## Usage

### Running Jupyter Notebooks
To explore or train the model step-by-step, navigate to the `notebooks/` folder and open the desired notebook:
```sh
jupyter notebook notebooks/initial-modelling/initial_raw_modelling.ipynb
```

### Running Python Scripts
To preprocess data, train models, or evaluate model performance, execute the appropriate Python scripts directly:
```sh
python src/model_training.py
```

## Methodology
This project employs a semi-supervised learning approach to train a facies classification model using both labeled and unlabeled datasets. Below are the key steps in the methodology:

1. **Initial Model Training**: Several machine learning models were tested, and Gradient Boosting was selected as the best-performing model based on initial results.

2. **Semi-Supervised Learning**: A base model was trained on the labeled data, and the model was then used to iteratively predict labels for the unlabeled datasets. These newly labeled datasets were added to the training data to augment and refine the model.

3. **Optimization**: Various optimization techniques, such as Grid Search, Randomized Search, Simulated Annealing, and Bayesian Optimization, were employed to enhance model performance. Simulated Annealing was found to be the most effective, leading to the highest observed accuracy.

For a more comprehensive explanation, please refer to the `methodology.md` file in the `docs/` folder.

## Results
The project involved testing multiple machine learning models and optimizing the best-performing model to achieve high accuracy in facies classification. Key findings include:

- **Gradient Boosting** was the best-performing model, achieving an Area Under the Curve (AUC) score of 0.991 and an accuracy of 93.8%.
- **Simulated Annealing** optimization resulted in the highest overall accuracy, reaching 96.79% for facies classification.
- **Accuracy Stability**: The iterative process of semi-supervised labeling demonstrated stability, with accuracy fluctuations well within acceptable limits throughout the labeling iterations.

For a detailed summary of results, refer to the `results_summary.md` file in the `docs/` folder.

## Acknowledgments
We acknowledge the confidential nature of the data used in this project, which limits our ability to include or disclose the original datasets. However, the methodology and approach have been generalized for illustrative purposes, providing insights into the workflows and techniques used.

## Contributing
We welcome contributions to this project! If you have any suggestions for improving the code or methodology, please feel free to submit a pull request or open an issue. Before contributing, ensure that any changes adhere to the confidentiality requirements.

## Contact
For any questions or further information, please contact:
- **Pranav Pant**: [pranavpant26@gmail.com](mailto:pranavpant26@gmail.com)

We look forward to your feedback and collaboration!
