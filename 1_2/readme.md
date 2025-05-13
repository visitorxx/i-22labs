Варіант 7: Airfoil Self-Noise Dataset
Опис: Прогнозування рівня шуму крила літака на основі різних параметрів.
Джерело даних: UCI Airfoil Self-Noise Dataset
Отримання та використання даних:
1.	Завантажте файл даних з https://archive.ics.uci.edu/ml/machine-learning-databases/00291/airfoil_self_noise.dat
2.	Дані представлені у текстовому форматі з розділювачами-табуляціями
3.	Використовуйте pandas для завантаження даних:
import pandas as pd
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/00291/airfoil_self_noise.dat"
column_names = ['Frequency', 'Angle_of_Attack', 'Chord_Length', 'Free_Stream_Velocity', 'Suction_Side_Displacement_Thickness', 'Sound_Pressure_Level']
df = pd.read_csv(url, sep='\t', names=column_names)
# Виберіть features (X) та цільову змінну (y)
X = df.iloc[:, :-1].values  # Всі колонки крім останньої
y = df.iloc[:, -1].values   # Остання колонка - рівень шуму
Рекомендовані параметри для початку:
•	w_init = np.zeros(X.shape[1])
•	b_init = 0
•	alpha = 0.0001
•	iterations = 2000
