# E-Commerce Customer Behavior Analysis and Churn Prediction Using Deep Learning

## 📌 Project Overview

This project focuses on analyzing customer behavior in an e-commerce platform and predicting customer churn using Deep Learning.

Customer churn refers to customers who stop engaging with a business, according to the churn definition provided in the dataset. By analyzing customer characteristics such as tenure, preferred login device, payment method, satisfaction score, order count, complaints, and cashback amount, this project explores patterns associated with customer churn.

The project combines **Exploratory Data Analysis (EDA), Data Visualization, Data Preprocessing, and a Multilayer Perceptron (MLP) Neural Network** to understand customer behavior and predict churn.

## 🎯 Objectives

- Analyze a real-world e-commerce customer dataset.
- Identify missing values, duplicates, and potential outliers.
- Perform data cleaning and preprocessing.
- Visualize customer behavior using statistical charts.
- Explore relationships between customer features and churn.
- Develop a deep learning model to predict customer churn.
- Evaluate model performance using classification metrics.
- Identify opportunities for improving customer retention.

## 📊 Dataset Description

**Dataset name:** E-Commerce Customer Churn Dataset

**Original file:** `E Commerce Dataset.xlsx`

**Worksheet used:** `E Comm`

**Dataset source:** [Kaggle – E-Commerce Customer Churn Dataset](https://www.kaggle.com/code/wonderdavid/e-commerce-customer-churn-prediction/data)

The dataset contains **5,630 customer records and 20 columns**.

### Important Features

| Feature | Description |
|---|---|
| CustomerID | Unique customer identifier |
| Churn | Target variable for churn prediction |
| Tenure | Customer tenure |
| PreferredLoginDevice | Preferred login device |
| CityTier | City classification |
| WarehouseToHome | Distance from warehouse to home |
| PreferredPaymentMode | Preferred payment method |
| Gender | Customer gender category |
| HourSpendOnApp | Time spent on the application |
| NumberOfDeviceRegistered | Number of registered devices |
| PreferedOrderCat | Preferred order category |
| SatisfactionScore | Customer satisfaction score |
| MaritalStatus | Marital-status category |
| NumberOfAddress | Number of registered addresses |
| Complain | Complaint indicator |
| OrderAmountHikeFromlastYear | Change in order amount |
| CouponUsed | Number of coupons used |
| OrderCount | Number of orders |
| DaySinceLastOrder | Days since the last order |
| CashbackAmount | Cashback amount |

The target variable is `Churn`:

- `0` – Non-churn customer
- `1` – Churn customer

The `CustomerID` field is excluded from the model inputs because it is an identifier.

## 🛠️ Technologies Used

- **Python** – Programming language
- **Google Colab** – Development environment
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical computation
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Scikit-learn** – Data preprocessing, splitting, and evaluation
- **TensorFlow/Keras** – Deep learning model development
- **GitHub** – Version control and project hosting

## 🔍 Exploratory Data Analysis

The following analyses and visualizations are included:

1. Dataset structure and statistical summary.
2. Missing-value analysis.
3. Duplicate-record checking.
4. Customer churn distribution.
5. Numerical feature distributions.
6. Categorical feature distributions.
7. Correlation heatmap.
8. Numerical feature comparison by churn status.
9. Outlier analysis using boxplots.
10. Churn-rate comparisons across customer categories.

These visualizations help identify patterns in customer characteristics and guide the preprocessing and modeling stages.

## 🧹 Data Preprocessing

The following preprocessing steps are performed:

- Remove duplicate records if any are present.
- Clean column names and text values.
- Handle missing numerical values using median imputation.
- Handle missing categorical values using most-frequent-value imputation.
- Detect potential numerical outliers using the Interquartile Range (IQR) method.
- Cap numerical outliers using limits learned from training data.
- Encode categorical variables using One-Hot Encoding.
- Standardize numerical features using StandardScaler.
- Exclude the customer identifier from model inputs.
- Split the dataset into training, validation, and testing sets.
- Apply class weights to address target-class imbalance.

The data is divided into approximately 64% training, 16% validation, and 20% testing data. Preprocessing is fitted on the training set to reduce data leakage.

## 🧠 Deep Learning Model

A **Multilayer Perceptron (MLP)** is developed using TensorFlow/Keras for binary classification.

### Model Architecture

- Input layer – receives the preprocessed features.
- Hidden layer 1 – 64 neurons with ReLU activation.
- Dropout layer – dropout rate of 0.20.
- Hidden layer 2 – 32 neurons with ReLU activation.
- Dropout layer – dropout rate of 0.10.
- Output layer – one neuron with sigmoid activation.

### Training Configuration

- Optimizer: Adam
- Loss function: Binary Cross-Entropy
- Batch size: 32
- Maximum epochs: 50 for the initial model
- Early stopping: Used to monitor validation loss
- Class weighting: Used to help address class imbalance

Basic hyperparameter tuning compares different hidden-layer sizes and learning rates using validation performance.

## 📈 Model Evaluation

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

The following visualizations are generated to evaluate model performance:

- Training loss vs. validation loss
- Training accuracy vs. validation accuracy
- Confusion matrix
- ROC curve
- Predicted churn probability distribution
- Exploratory feature-weight analysis

### Results

The recorded evaluation results are:

| Metric | Result |
|---|---:|
| Test Loss | 0.2146 |
| Test Accuracy | 91.39% |
| Precision | 69.14% |
| Recall | 88.42% |
| F1-score | 77.60% |
| ROC-AUC | 0.9669 |

These results indicate promising classification performance on the available test dataset. Precision, recall, and F1-score are included because accuracy alone may not adequately describe performance on an imbalanced dataset.

Results may vary if the model is retrained with different settings or random states.

## 💻 How to Run the Project

### Option 1: Run in Google Colab

1. Download or obtain the original Excel dataset from the dataset source.
2. Open [Google Colab](https://colab.research.google.com/).
3. Upload the project notebook (`.ipynb`) or create a new notebook.
4. Upload `E Commerce Dataset.xlsx` to the Colab session.
5. Install any missing libraries if required.
6. Run the notebook cells in order.
7. Review the EDA visualizations, preprocessing output, model training history, and final evaluation metrics.

### Option 2: Run Locally

**Step 1: Clone the repository**

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

Replace `YOUR-USERNAME` and `YOUR-REPOSITORY` with your GitHub details.

**Step 2: Install the required libraries**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow openpyxl joblib jupyter
```

**Step 3: Place the dataset in the project folder**

Ensure that `E Commerce Dataset.xlsx` is in the same directory as the notebook, or update the dataset path in the code.

**Step 4: Start Jupyter Notebook**

```bash
jupyter notebook
```

**Step 5: Open and execute the notebook**

Run the cells sequentially to perform EDA, preprocess the data, train the neural network, and evaluate the model.

## 📁 Project Structure

```text
E-Commerce-Customer-Churn/
│
├── README.md
├── Ecommerce_Customer_Churn_Analysis.ipynb
├── E Commerce Dataset.xlsx
├── report.pdf
├── cleaned_ecommerce_data.csv
├── final_model_metrics.csv
├── hyperparameter_tuning_results.csv
├── ecommerce_churn_model.keras
├── ecommerce_preprocessor.pkl
│
└── visualizations/
    ├── churn_distribution.png
    ├── correlation_heatmap.png
    ├── training_loss.png
    ├── training_accuracy.png
    ├── confusion_matrix.png
    └── roc_curve.png
```

This structure is illustrative. Include only files that actually exist in your repository. The original dataset, cleaned dataset, trained model, and preprocessing pipeline are optional repository files; use the source link instead if redistribution is restricted.

## 💡 Applications

- Customer-retention analysis
- Identification of customer groups with elevated churn rates
- Analysis of customer complaints and purchasing patterns
- Support for customer-engagement planning
- Exploration of data-driven e-commerce business strategies

The model's predictions should be validated before being used to make real business decisions.

## 🚀 Future Enhancements

- Compare the MLP with Random Forest, Logistic Regression, and Gradient Boosting.
- Use SHAP or permutation importance for more reliable feature interpretation.
- Optimize the classification threshold based on business objectives.
- Standardize equivalent categorical labels.
- Evaluate performance on newer customer data.
- Build an interactive dashboard for customer behavior analysis.
- Investigate whether targeted retention strategies improve customer outcomes.

## 👩‍💻 Author

**Name:** [Your Name]  
**Department:** Artificial Intelligence and Data Science  
**Institution:** [Your College Name]

## 📄 License and Dataset Attribution

This project is intended for educational and academic purposes. Refer to the original dataset source for its applicable license and redistribution terms. Ensure that any third-party dataset, code, or other material included in the repository is used in accordance with its license.

## 🙏 Acknowledgements

Thanks to the dataset contributors and the developers of Python, Pandas, Scikit-learn, TensorFlow, Matplotlib, and Seaborn for providing the tools used in this project.
