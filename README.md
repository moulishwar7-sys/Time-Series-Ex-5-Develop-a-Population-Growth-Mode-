# Time-Series-Ex-5-Develop-a-Population-Growth-Mode-

# AIM:
To develop a simple mathematical model for population growth using Python and use the model to predict future population.

# PROGRAM:
```
import matplotlib.pyplot as plt
import numpy as np

# Historical financial data
year = np.array([2020, 2021, 2022, 2023, 2024])
revenue = np.array([50.0, 55.5, 62.0, 68.0, 74.5]) # In millions USD

# Time indices (t = 0 to 4)
t = np.arange(len(year))

# Fit 1st-degree polynomial: slope (b), intercept (a)
b, a = np.polyfit(t, revenue, 1)

# In-sample predictions
predicted_revenue = a + b * t
print(f"Base Revenue (a): {a:.2f}M")
print(f"Annual Growth Rate (b): {b:.2f}M/year")
print("\nYear Actual ($M) Predicted ($M)")
for y, act, pred in zip(year, revenue, predicted_revenue):
 print(f"{y} {act:10.2f} {pred:14.2f}")

# Future forecasting
future_year = np.array([2025, 2026, 2027])
future_t = np.array([5, 6, 7])
future_revenue = a + b * future_t
print("\nForecasted Revenue:")
for fy, f_rev in zip(future_year, future_revenue):
 print(f"{fy}: ${f_rev:.2f}M")

# Visualization
plt.plot(year, revenue, 'o-', label='Actual Revenue')
plt.plot(year, predicted_revenue, 'x--', label='Fitted Model')
plt.plot(future_year, future_revenue, 's:', label='Forecast')
plt.title("Company Revenue Growth Model")
plt.xlabel("Year")
plt.ylabel("Revenue ($ Millions)")
plt.legend()
plt.grid(True)
plt.show()
```

# OUTPUT:

<img width="561" height="552" alt="image" src="https://github.com/user-attachments/assets/dc2735ab-e218-4f65-81f3-82010bff2650" />



