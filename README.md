# Employee-Attrition-Prediction
Machine Learning project for employee attrition prediction
## Project Goal

* Build an end-to-end machine learning pipeline to predict employee attrition risk, allowing HR teams to proactively deploy retention strategies.

---

## Dataset & Preprocessing

* The raw dataset contained 10,050 records and 26 features covering demographics, job roles, and employee satisfaction.


* Rows missing the `Attrition` target label (891 records) were completely removed to eliminate training bias.


* Categorical entries were standardized and missing values were handled using mode imputation.


* Erroneous negative ages were converted to positive values (mean imputed), currency strings were converted to numbers, and remaining numeric gaps were handled using median imputation.


* Non-predictive IDs and duplicates were removed, leaving a final clean dataset of 9,132 unique employees.


* The clean data exhibited a strong class imbalance, with 7,313 employees who stayed and 1,819 who left.

---

## Modeling & Deployment

* Data was divided into independent train and test sets to maintain an uncorrupted validation environment.


* Synthetic Minority Over-sampling Technique (SMOTE) was applied strictly to the training data to balance the classes.


* Classification algorithms were trained and hyperparameter-tuned to optimize model Recall for the attrition class.


* Feature importance scores were extracted to rank the primary workplace drivers of employee turnover.


* The finalized model and preprocessing scalers were serialized and deployed into an interactive Streamlit web application (`app.py`) for real-time risk scoring.

---

## Technical Implementation Details

* **Feature Engineering & Encoding:** Categorical variables (such as `Department`, `EducationField`, and `JobRole`) were transformed into numerical formats using One-Hot Encoding, while ordinal features (like `BusinessTravel`) were mapped using Label Encoding to preserve structural order.


* **Feature Scaling:** Numeric attributes with varying ranges (such as `Monthly_Income` and `Age`) were normalized using standard scaling techniques to prevent features with larger scales from dominating the distance calculations in the models.


* **Cross-Validation:** To prevent overfitting and guarantee stable generalization, the tuned models were validated using $K$-fold cross-validation on the balanced training subset before final evaluation on the holdout test set.

---

## Business Impact & Insights

* **Actionable Risk Metrics:** The Streamlit application outputs a precise probability score rather than a simple binary classification, allowing HR professionals to prioritize interventions for employees sitting in the highest risk brackets.

TEAM MEMBERS:
Joice Mina Refaat
Zamzam Mohamad Nasser
Malak Elhusany
Ahmed Mohsen
Ahmed Alkhatib
* **Data-Driven Retention:** By analyzing the top features driving the model's decisions (such as high overtime hours paired with low stock option levels), management can pinpoint systemic organizational issues and adjust corporate policies to improve overall workplace satisfaction.
