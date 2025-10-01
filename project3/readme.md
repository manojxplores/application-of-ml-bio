# README: Decision Tree Classification on Breast Cancer SEER Dataset

## 📌 Objective

This project trains a **Decision Tree classifier** on SEER breast cancer patient data to predict the **Status (Alive/Dead)** of patients.
It also simulates “epochs” by varying the **tree depth from 1 to 20**, and plots **training/validation accuracy** and **loss curves**.
Finally, it visualizes the best decision tree with feature splits and class labels.

---

## 📂 Dataset

* The dataset contains records of female breast cancer patients (2006–2010).
* Input features include **Age, Race, Marital Status, Tumor Stage, Grade, Tumor Size, Hormone Receptor Status, etc.**
* Target variable: **Status (Alive / Dead)**.

⚠️ The feature `Survival Months` is **dropped** before training because it causes **data leakage** (post-diagnosis survival duration directly reveals outcome).

---

## ⚙️ Requirements

Make sure you have Python 3.8+ and install the following dependencies:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

## ▶️ How to Run

1. Place your dataset CSV file (with columns like *Age, Race, Marital Status, T Stage, …, Status*) in the project folder.
   Example name: `seer_breast_cancer.csv`.

2. Update the code to read your CSV file:

   ```python
   df = pd.read_csv("seer_breast_cancer.csv")
   ```

3. Run the script (`python decision-tree.py` or in Jupyter Notebook).
   The script will:

   * Clean the dataset (`Grade` column fixed, `Survival Months` removed).
   * Encode categorical and numerical variables using **OneHotEncoder** + **StandardScaler**.
   * Train Decision Tree models at depths 1 → 20.
   * Plot:

     * **Training vs Validation Accuracy**
     * **Training vs Validation Loss**

---

## 📊 Output

**Accuracy & Loss Curves**
   A line plot showing:

   * Training Accuracy vs Depth (epochs)
   * Validation Accuracy vs Depth
   * Training/Validation Loss (1 – accuracy)
