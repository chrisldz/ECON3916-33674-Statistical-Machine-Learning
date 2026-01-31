# 📊 The Student Inflation Reality Check

## 📌 Project Overview

Official inflation statistics represent national averages, but individual experiences of inflation can vary dramatically depending on location and spending patterns. This project investigates how inflation impacts a college student living in Boston compared to both the national average and the local Boston CPI.

By constructing a custom **Student Spending Index (SPI)** and comparing it to official CPI data, this analysis reveals how different consumption weights lead to very different inflation realities.

---

## 🧠 Key Questions

- Does the official CPI reflect the real inflation experienced by students?
- How does inflation in Boston compare to the U.S. average?
- What happens when we adjust inflation weights to match a student’s spending habits?

---

## 🔧 Methodology

1. Built a custom **Student Basket** including tuition, rent, food away from home, and streaming services.
2. Calculated inflation manually using price changes from 2016 to 2024.
3. Pulled official CPI data from FRED (Federal Reserve Economic Data).
4. Normalized all indices to **2016 = 100** for fair comparison.
5. Created a **Student-Specific Price Index (SPI)** using weighted components.
6. Extended the analysis with AI to include **Boston regional CPI**.

---

## 📊 Results

The analysis reveals three important insights:

- **Boston inflation is higher than the U.S. national average**, showing how national CPI can understate urban cost pressures.
- **Student inflation is higher than both Boston and national CPI**, driven by high-weight categories such as tuition and rent.
- The official CPI is not incorrect, but it **fails to represent subgroup-specific inflation realities**.

---

## 💡 Key Takeaway

Inflation is not one number. It depends on *who you are* and *where you live*. Students in major cities experience significantly higher cost-of-living increases than national averages suggest.

---

## 🛠 Tools Used

- Python  
- Pandas  
- Matplotlib  
- FRED API  
- Generative AI for advanced expansion  

---

## 📁 Files in This Project

| File | Description |
|------|-------------|
| notebook.ipynb | Full analysis including manual CPI construction and AI expansion |
| README.md | Project overview and findings |

---

## 👨‍🎓 Author

Data analysis project exploring real-world inflation impacts on student life.
