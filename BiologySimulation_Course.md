# Python for Biology Simulations: A modeling Tutorial

Explore the dynamic world of biological systems through the lens of Python. This course will teach you to model populations, chemical reactions, and evolutionary processes.

---

## 1. Mathematical Modeling Basics
Modeling starts with translating biology into math. For example, the rate of change of a population $N$ over time $t$:
$$\frac{dN}{dt} = rN$$
Where $r$ is the growth rate.

---

## 2. Modeling Population Dynamics

### Exponential and Logistic Growth
Python is perfect for visualizing how populations grow when resources are limited.
```python
import numpy as np
import matplotlib.pyplot as plt

def logistic_growth(N, r, K):
    return r * N * (1 - N / K)

# Simulation parameters
r = 0.1    # growth rate
K = 1000   # carrying capacity
N = 10     # initial population
time = np.linspace(0, 100, 1000)

# Simplistic Euler method for simulation
dt = time[1] - time[0]
pop_history = []
for _ in time:
    pop_history.append(N)
    N += logistic_growth(N, r, K) * dt

plt.plot(time, pop_history)
plt.title("Logistic Population Growth")
plt.show()
```

### Predator-Prey (Lotka-Volterra)
Model the interaction between two species.
```python
from scipy.integrate import odeint

def lotka_volterra(y, t, alpha, beta, delta, gamma):
    prey, pred = y
    dprey_dt = alpha * prey - beta * prey * pred
    dpred_dt = delta * prey * pred - gamma * pred
    return [dprey_dt, dpred_dt]

# Parameters & Initial Conditions
y0 = [10, 5] # [prey, predators]
t = np.linspace(0, 50, 1000)
params = (1.1, 0.4, 0.1, 0.4)

sol = odeint(lotka_volterra, y0, t, args=params)
plt.plot(t, sol[:, 0], label='Prey')
plt.plot(t, sol[:, 1], label='Predator')
plt.legend()
plt.show()
```

---

## 3. Computational Biochemistry

### Enzyme Kinetics (Michaelis-Menten)
Model how fast enzymes convert substrates.
```python
def michaelis_menten(S, Vmax, Km):
    return (Vmax * S) / (Km + S)

S = np.linspace(0, 100, 100)
V = michaelis_menten(S, 10, 20)
plt.plot(S, V)
plt.xlabel("Substrate Concentration [S]")
plt.ylabel("Reaction Velocity V")
plt.show()
```

---

## 4. Bio-inspired Algorithms
### Simple Genetic Algorithm Concept
Genetic Algorithms (GAs) mimic natural selection to find solutions to optimization problems.
1.  **Population**: A set of candidate solutions.
2.  **Fitness**: How "good" a solution is.
3.  **Selection**: Choosing the best solutions to "breed".
4.  **Crossover & Mutation**: Creating new solutions from parents.

---

## 5. Tools of the Trade
- **NetworkX**: For Protein-Protein Interaction (PPI) networks.
- **Biopython**: For DNA/Protein sequence analysis.
- **PyDEVS**: For discrete event simulation.

---

## 6. Project: The SIR Model
Develop a script that simulates an epidemic by tracking:
- **S**usceptible individuals
- **I**nfected individuals
- **R**ecovered individuals

This involves solving a system of three differential equations using `odeint`.

---
[Return to Main README](README.md)
