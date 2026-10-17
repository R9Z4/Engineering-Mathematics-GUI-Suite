# Engineering Mathematics GUI Suite (MATLAB App Designer)

An interactive computational suite developed in **MATLAB App Designer** for multivariable calculus, coordinate transformations, and state-space numerical/analytical solutions of $n$-th order linear differential equations.

Developed at the Department of Electrical Engineering, **Ferdowsi University of Mashhad (FUM)**.

---

## Suite Applications

The suite comprises two standalone graphical engineering tools:

1. **Multivariate Integral Calculator (`Multivariate_Integral_Calculator.mlapp`)**
2. **$N$-th Order ODE State-Space Solver (`Nth_Order_ODE_StateSpace_Solver.mlapp`)**

---

## 1. Multivariate Integral Calculator

An interactive computational engine designed to evaluate single, double, and triple integrals in various curvilinear coordinate systems with real-time mathematical typesetting.

### Key Capabilities
- **Coordinate Transformations & Automatic Jacobian Scaling:**  
  Supports evaluation in Cartesian, Cylindrical, and Spherical coordinate systems. Automatically incorporates coordinate metric determinants:
  - **Cartesian:** $dV = dx \, dy \, dz$
  - **Cylindrical:** $dV = r \, dr \, d\theta \, dz \quad (\text{Scale factor: } r)$
  - **Spherical:** $dV = \rho^2 \sin(\phi) \, d\rho \, d\theta \, d\phi \quad (\text{Scale factor: } \rho^2 \sin(\phi))$
- **Dynamic LaTeX Typesetting:**  
  Renders mathematical expressions dynamically as the user modifies integration orders and boundaries.
- **Dual Computation Engine:**  
  - **Analytical (Exact):** Nested symbolic integration using MATLAB's `int` engine.
  - **Numerical (High-Precision):** Variable-precision numerical quadrature via `vpa` / `vpaintegral`.
- **Graphical Surface Visualizer:**  
  Integrates 2D curve plotting (`fplot`) and 3D surface rendering (`fsurf`) for integrand and primitive function visualization.

---

## 2. $N$-th Order ODE State-Space Solver

A comprehensive solver for $n$-th order constant-coefficient linear ordinary differential equations, combining closed-form symbolic solutions with modern state-space numerical algorithms.

### Mathematical Formulation
For an $n$-th order differential equation:
$$a_n y^{(n)} + a_{n-1} y^{(n-1)} + \dots + a_1 y' + a_0 y = f(x)$$

The tool transforms the scalar $n$-th order equation into an equivalent first-order matrix system (State-Space Form):
$$\mathbf{\dot{x}}(t) = \mathbf{A} \mathbf{x}(t) + \mathbf{B} u(t)$$

where the state vector is defined as $\mathbf{x} = [x_1, x_2, \dots, x_n]^T = [y, y', \dots, y^{(n-1)}]^T$.

### Key Capabilities
- **State-Space Matrix Conversion:**  
  Converts arbitrary higher-order systems into companion matrix state-space equations, allowing solution via MATLAB's adaptive Runge-Kutta solver (`ode45`).
- **Exact Analytical Solutions:**  
  Computes symbolic closed-form transient and steady-state responses using `dsolve`.
- **Dynamic Equation String Generation:**  
  Parses user-selected order $n$ and coefficients dynamically, displaying the active equation and initial conditions.
- **Robust Exception Handling:**  
  Employs `try-catch` structures to validate input syntax, convergence criteria, and singular boundary conditions.

---

## File Structure

```
├── Multivariate_Integral_Calculator.mlapp   # Multivariable symbolic/numerical integral tool
├── Nth_Order_ODE_StateSpace_Solver.mlapp    # State-space & analytical ODE solver
├── Technical_Report.pdf                     # Comprehensive engineering report
└── README.md                                # Repository documentation
```

---

## How to Run

1. Open MATLAB (R2020b or later with Symbolic Math Toolbox).
2. Launch either application directly in MATLAB:
   ```matlab
   open('Multivariate_Integral_Calculator.mlapp')
   ```
   or
   ```matlab
   open('Nth_Order_ODE_StateSpace_Solver.mlapp')
   ```

---

## Author

- **Reza Roodi**  
- Department of Electrical Engineering, Ferdowsi University of Mashhad (FUM)
