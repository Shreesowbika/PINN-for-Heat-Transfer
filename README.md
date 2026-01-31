# **ThermoPINN**
### *Physics-Informed Neural Networks for Transient Heat Conduction*

ThermoPINN is a deep learning framework designed to solve the **2D transient heat conduction equation** in a copper plate using **Physics-Informed Neural Networks (PINNs)**.  
Built using the **DeepXDE** library, this project embeds the governing laws of thermodynamics directly into the neural network’s loss function, enabling accurate temperature field prediction **without traditional mesh-based solvers**.

The model’s predictions are **validated against high-fidelity Ansys Mechanical simulation data**, demonstrating the effectiveness of PINNs as an alternative to conventional Finite Element Analysis (FEA).

---

## Project Overview

In traditional engineering workflows, transient heat transfer problems are typically solved using **Finite Element Analysis (FEA)**. While highly accurate, FEA can be computationally expensive and time-consuming, especially for repeated simulations or inverse problems.

This project demonstrates how **Physics-Informed Neural Networks (PINNs)** can:

- Solve **Fourier’s Law of Heat Conduction** without explicit meshing
- Learn temperature evolution directly from **physics constraints**
- Validate predictions using **industrial-standard Ansys simulation data**
- Minimize prediction error across **spatial** \((x, y)\) and **temporal** \((t)\) domains

---

## Governing Physics

The model solves the **2D transient heat equation** derived from Fourier’s Law:

$$\frac{\partial T}{\partial t} = \alpha \left( \frac{\partial^2 T}{\partial x^2} + \frac{\partial^2 T}{\partial y^2} \right)$$

### Problem Setup

- **Material**: Copper plate  
- **Thermal Diffusivity** (\(\alpha\)): `117.0 mm²/s`  
- **Domain**: `20 mm × 20 mm` square plate  
- **Boundary Conditions**: Dirichlet boundary conditions  
- **Initial Conditions**: Extracted from Ansys transient simulation data  

---

## Tech Stack

- **Deep Learning**: DeepXDE, TensorFlow / Keras  
- **Scientific Computing**: NumPy, SciPy  
- **Validation Data**: Ansys Mechanical (Transient Thermal Analysis)  
- **Visualization**: Matplotlib  

---

## Results & Visualizations

The trained PINN produces the following outputs:

- **Temperature Contours**  
  - Spatio-temporal heat propagation across the copper plate  
- **Error Maps**  
  - Absolute difference between PINN predictions and Ansys results  
- **Training Dynamics**  
  - Loss convergence plots showing:
    - PDE residual minimization  
    - Boundary and initial condition enforcement  

These results demonstrate strong agreement between the PINN solution and Ansys benchmarks.
