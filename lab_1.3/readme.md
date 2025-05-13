Варіант 7: Кредитний скоринг (Credit Approval Dataset)
Опис: Класифікація заявок на кредит на "схвалені" та "відхилені".
Джерело даних: UCI Credit Approval Dataset
Код для завантаження:
import pandas as pd
from sklearn.preprocessing import LabelEncoder

url = "https://archive.ics.uci.edu/ml/machine-learning-databases/credit-screening/crx.data"
columns = [f"feature_{i}" for i in range(15)] + ["class"]
data = pd.read_csv(url, names=columns, na_values='?')
data = data.dropna()

# Кодування категоріальних змінних
for i in range(15):
    if data[f"feature_{i}"].dtype == 'object':
        le = LabelEncoder()
        data[f"feature_{i}"] = le.fit_transform(data[f"feature_{i}"])

X = data.iloc[:, :-1].values
y = (data['class'] == '+').astype(int)

