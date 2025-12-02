# 🩸 Blood Transfusion Data Analysis 🩺

This project analyzes a blood donation dataset from a mobile blood donation service in Taiwan and builds a machine learning model to predict whether donors will give blood in future drives. Accurate prediction of donor behavior can help healthcare providers plan blood drives efficiently and ensure sufficient blood supply.

## 📊 Dataset

The dataset comes from the Blood Transfusion Service Center in Taiwan, which collects blood from donors at universities. It is structured according to the **RFMTC model**, a variation of the RFM marketing model, with the following features:

- **R (Recency):** Months since the last donation  
- **F (Frequency):** Total number of donations  
- **M (Monetary):** Total blood donated in c.c.  
- **T (Time):** Months since the first donation  
- **Target:** Binary variable indicating whether the donor gave blood in March 2007 (1 = yes, 0 = no)

## 🛠️ Project Steps

1. **Data Loading and Inspection**  
   - Loaded the CSV dataset into a pandas DataFrame.  
   - Verified all columns are numeric and there are no missing values.  

2. **Target Column Preparation**  
   - Renamed the target column for simplicity.  
   - Checked class distribution: ~76% non-donors, ~24% donors.  

3. **Train/Test Split**  
   - Split the data into training and test sets while maintaining class distribution using stratification.  

4. **Automated Model Selection with TPOT**  
   - Used TPOT, an AutoML library, to explore and select the best-performing pipeline.  
   - Logistic Regression was selected as the optimal model.  

5. **Variance Check and Log Normalization**  
   - Identified high variance in the monetary feature.  
   - Applied log normalization to reduce variance and balance feature influence.  

6. **Model Training and Evaluation**  
   - Trained a logistic regression model on normalized features.  
   - Achieved an **AUC score of ~0.785**, outperforming a naive baseline model.  

## 🧰 Tools & Libraries

- Python  
- Pandas & NumPy (data manipulation)  
- Scikit-learn (train/test split, logistic regression, evaluation metrics)  
- TPOT (automated machine learning pipeline optimization)  
- Jupyter Notebook / Google Colab (data exploration and model training)  

## ▶️ How to Run

1. Open the notebook in [Google Colab](https://colab.research.google.com/).  
2. Upload `transfusion.data` to the Colab environment.  
3. Run all cells to reproduce the analysis and results.  

## ✅ Conclusion

Predicting blood donor behavior helps optimize blood donation campaigns and ensures sufficient blood supply, potentially saving lives. Logistic regression offers interpretability and a solid baseline, while automated pipeline selection using TPOT can enhance model selection efficiency.
