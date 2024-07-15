# Prasunet_DS_01

# Prasunet_DS_01
# scripts/create_dataset.py
import pandas as pd

data = {
    'age': [23, 45, 22, 34, 42, 54, 25, 23, 33, 45, 26, 27, 32, 34, 30, 31, 29, 28, 27, 26],
    'gender': ['male', 'female', 'female', 'male', 'female', 'male', 'female', 'male', 'female', 'male', 'female', 'male', 'female', 'male', 'female', 'male', 'female', 'male', 'female', 'male']
}

df = pd.DataFrame(data)

csv_path = 'C:/Users/shell/Downloads/API_SP.POP.TOTL_DS2_en_csv_v2_739890.csv'
df.to_csv(csv_path, index=False)
print(f"Dataset saved to {csv_path}")

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

csv_path = 'C:/Users/shell/Downloads/API_SP.POP.TOTL_DS2_en_csv_v2_739890.csv'
df = pd.read_csv(csv_path)

# Bar Chart for Gender Distribution
gender_counts = df['gender'].value_counts()

fig1, ax1 = plt.subplots(figsize=(10, 6))
sns.barplot(x=gender_counts.index, y=gender_counts.values, palette='viridis', ax=ax1)
ax1.set_xlabel('Gender')
ax1.set_ylabel('Count')
ax1.set_title('Distribution of Genders in the Population')
gender_chart_path = 'C:/Users/shell/Downloads/API_SP.POP.TOTL_DS2_en_csv_v2_739890/output/gender_distribution.png'
plt.show()

# Histogram for Age Distribution
fig2, ax2 = plt.subplots(figsize=(10, 6))
sns.histplot(df['age'], bins=10, kde=True, color='blue', ax=ax2)
ax2.set_xlabel('Age')
ax2.set_ylabel('Frequency')
ax2.set_title('Distribution of Ages in the Population')
age_chart_path = 'C:/Users/shell/Downloads/API_SP.POP.TOTL_DS2_en_csv_v2_739890/age_distribution.png'
plt.show()
