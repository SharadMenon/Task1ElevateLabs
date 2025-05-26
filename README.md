# Titanic Dataset Preprocessing - Task 1

This project involves preprocessing the Titanic dataset to prepare it for machine learning tasks. The steps include data exploration, handling missing values, encoding categorical variables, normalization, outlier detection and removal, and ensuring dummy variable trap is avoided.

---

## ✅ 1. Importing and Exploring the Dataset

* Loaded the Titanic dataset using `pandas.read_csv()`.
* Set `PassengerId` as the DataFrame index for better row referencing.
* Used `.info()`, `.describe()`, and `.isna().sum()` to explore column data types, statistical summaries, and missing values.

---

## ✅ 2. Handling Missing Values

* Used `.fillna()` to impute missing values:

  * `Age` was filled with its **mean**, rounded to 1 decimal place.
  * `Cabin` was filled with the placeholder value **"No Cabin"**.

---

## ✅ 3. Encoding Categorical Variables

* Applied **One-Hot Encoding** using `pd.get_dummies()` to convert the `Embarked` column into numeric format.
* **Dummy Variable Trap was prevented** by dropping the first dummy column (`drop_first=True`).
* (Optional) `LabelEncoder` was imported for future use with ordinal columns but not applied in this notebook.

---

## ✅ 4. Normalization / Standardization

* Used `StandardScaler` from `sklearn.preprocessing` to standardize the `Fare` column.
* Ensured proper input shape by passing `[['Fare']]` (2D array) to `fit_transform()`.

---

## ✅ 5. Outlier Detection and Removal

* Visualized outliers in the `Fare` column using **Seaborn boxplots**.
* Used the **IQR method** to detect and remove outliers:

  * Calculated Q1, Q3, and IQR
  * Defined bounds as: `Q1 - 1.5*IQR` and `Q3 + 1.5*IQR`
  * Filtered out rows outside this range
* Plotted a second boxplot to confirm successful outlier removal.

---

## ✅ 6. Saving the Processed Dataset

* Final cleaned DataFrame was saved as `Processed_Dataset.csv` using `df_encoded.to_csv()`.

---

## Summary Table

| Task                          | Status |
| ----------------------------- | ------ |
| Data import & exploration     | ✅ Done |
| Missing value handling        | ✅ Done |
| Categorical encoding          | ✅ Done |
| Prevent dummy variable trap   | ✅ Done |
| Normalization/Standardization | ✅ Done |
| Outlier detection/removal     | ✅ Done |

---

