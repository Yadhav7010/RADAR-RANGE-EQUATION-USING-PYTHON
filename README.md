# EVALUATION-OF-RADAR-RANGE-USING-PYTHON

---

## Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

---

## Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target.

<img width="573" height="442" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

---

## Procedure:
1. Set up the Python environment  
2. Import necessary libraries  
3. Define the Radar Range Equation  
4. Input radar parameters  
5. Calculate maximum range  
6. Execute the program  

---

## Algorithm:
1. Define constants: Pt, Gt, Gr, λ, σ, Pmin  
2. Use Radar Range Equation to compute Rmax  
3. Vary parameters (Pt, Gt, Pmin)  
4. Plot Rmax against each parameter  
5. Analyze variation  

---

## PROGRAM
```python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
Gr = 25
lm = 0.03
sigma = 5
pmin_base = 1e-12
Gt_base = 30
Pt_base = 2000

plt.figure(figsize=(10, 12))

# Rmax vs Pt
Pt1 = np.arange(1, 5001, 10)
Rmax1 = (((Pt1 * Gt_base * Gr * (lm**2) * sigma) / (((4 * np.pi)**2) * pmin_base)))**(1/4)

plt.subplot(3, 1, 1)
plt.plot(Pt1, Rmax1)
plt.title('Rmax vs Pt (Gt=30, Pmin=1e-12)')
plt.xlabel('Pt (Transmitted Power)')
plt.ylabel('Rmax (Maximum Range)')
plt.grid(True)

# Rmax vs Gt
Gt2 = np.arange(1, 61, 1)
Rmax2 = (((Pt_base * Gt2 * Gr * (lm**2) * sigma) / (((4 * np.pi)**2) * pmin_base)))**(1/4)

plt.subplot(3, 1, 2)
plt.plot(Gt2, Rmax2)
plt.title('Rmax vs Gt (Pt=2000, Pmin=1e-12)')
plt.xlabel('Gt (Transmitter Gain)')
plt.ylabel('Rmax (Maximum Range)')
plt.grid(True)

# Rmax vs Pmin
pmin3 = np.logspace(-15, -9, 200)
Rmax3 = (((Pt_base * Gt_base * Gr * (lm**2) * sigma) / (((4 * np.pi)**2) * pmin3)))**(1/4)

plt.subplot(3, 1, 3)
plt.plot(pmin3, Rmax3)
plt.xscale('log')
plt.title('Rmax vs Pmin (Pt=2000, Gt=30)')
plt.xlabel('Pmin (Minimum Detectable Power)')
plt.ylabel('Rmax (Maximum Range)')
plt.grid(True)

plt.tight_layout()
plt.show()
```

---

## OUTPUT
<img width="989" height="1189" src="https://github.com/user-attachments/assets/568f540a-a4be-4cd7-947c-3fdfa3b30734" />

---

## TABULATION
<img width="1600" height="1541" src="https://github.com/user-attachments/assets/82045c6c-f381-44bd-8e7c-6a5f3404ffe8" />

---

## RESULT:
Thus the maximum radar range was calculated using the Radar Range Equation in Python, and the variation of range with transmitted power, transmitter gain, and minimum detectable power was successfully analyzed and verified.
<img width="1073" height="477" alt="image" src="https://github.com/user-attachments/assets/54641f3f-a570-46f9-93bb-bea89f8616f7" />
