# Lid Driven Cavity Flow Simulation README.md

Here is your **final detailed README.md content** exported for direct download.

---

## 📌 Problem Statement

This repository contains a Python implementation to solve the **flow inside a two-dimensional lid driven cavity** using the **vorticity-stream function formulation**.

The problem simulates a square cavity with:

- The **top lid moving** at a constant velocity in the x-direction.
- **No-slip boundary conditions** on all walls.
- **Incompressible, viscous fluid flow** governed by the Navier-Stokes equations reformulated into vorticity-stream function form.

---

## ✨ Features

✅ User input for grid size, Reynolds number, and lid velocity\
✅ Explicit time marching for the vorticity transport equation\
✅ Implicit Gauss-Seidel iteration for solving the stream function Poisson equation\
✅ Visualization of **stream function contours**, **vorticity contours**, and **velocity field**

---

## 🧮 Mathematical Formulation

### **Assumptions**

1. Lid moves in the x-direction only.
2. Plate moves with constant velocity \(U_{top}\) starting at \(t = 0\).
3. Fluid is **viscous and incompressible**.

### **Equations**

#### **Vorticity Transport Equation**

Discretized using **explicit time marching**:

$$
\omega^{n+1}_{i,j} = \omega^n_{i,j}
- \Delta t \left( u \frac{\partial \omega}{\partial x}
+ v \frac{\partial \omega}{\partial y} \right)
+ \nu \Delta t \left( \frac{\partial^2 \omega}{\partial x^2}
+ \frac{\partial^2 \omega}{\partial y^2} \right)
$$

#### **Stream Function Poisson Equation**

Solved using **Gauss-Seidel iteration**:

$$
\nabla^2 \psi = -\omega
$$

### **Boundary Conditions**

- **Top wall (lid)**: \(\psi = 0\), \(\omega = -2U_{top}/dy\)
- **Bottom wall**: \(\psi = 0\), \(\omega = 0\)
- **Left and right walls**: \(\psi = 0\), \(\omega = 0\)

---

## 💻 Code Structure

- **Inputs:**

  - Grid size in x and y directions
  - Reynolds number
  - Lid velocity

- **Initialization:**

  - Stream function (`psi`)
  - Vorticity (`omega`)
  - Velocity fields (`Vx`, `Vy`)

- **Main Time-Stepping Loop:**

  1. Compute velocities from stream function.
  2. Update vorticity using the transport equation.
  3. Apply boundary conditions.
  4. Solve the Poisson equation for stream function using **Gauss-Seidel iteration** until convergence.

- **Visualization:**

  - Stream function contours
  - Vorticity contours
  - Velocity vector field

---

## 📝 Usage

### **Requirements**

- Python 3.x
- numpy
- matplotlib

Install dependencies via:

```bash
pip install numpy matplotlib
```

### **Run the Simulation**

```bash
python lid_driven_cavity.py
```

Follow the prompts to enter:

- Grid size (e.g., 41 x 41)
- Reynolds number (e.g., 1000)
- Lid velocity (e.g., 1.0)

### **Outputs**

- **Stream function contours:** Visualizing flow patterns.
- **Vorticity contours:** Showing rotational behavior of fluid.
- **Velocity field:** Quiver plot of flow velocity vectors.

---

## 📂 Files Included

| File                   | Description                                   |
| ---------------------- | --------------------------------------------- |
| `lid_driven_cavity.py` | Main Python script implementing the CFD code. |
| `CFDassignment2.pdf`   | Problem statement and equations.              |
| `README.md`            | Project description and instructions.         |

---

## 🎯 Applications

This code provides a foundation for:

- Benchmarking CFD codes
- Understanding incompressible flow in closed cavities
- Extending to other flow geometries using vorticity-stream function approaches

---

## 👨‍💻 Author

**MOHAMMED FAIZAN (SVNIT)**

---

## 🔗 References

- Computational Fluid Dynamics textbook formulations
- MIT OpenCourseWare CFD lecture notes
- Ferziger & Peric, *Computational Methods for Fluid Dynamics*

---

## 📝 License

This project is open-source for educational and academic learning purposes.

---

✅ **Download this updated .md file from canvas for your GitHub upload now.**

Let me know if you also need a LaTeX PDF with SVNIT branding for your records today.

