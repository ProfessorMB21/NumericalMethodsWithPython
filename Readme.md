# Numerical Methods: Spline Interpolation

## 📚 Overview

This repository contains implementations of spline interpolation methods completed as part of my computational mathematics coursework. The project demonstrates practical applications of numerical analysis techniques for function approximation using piecewise polynomials.

## 🏗️ Project Structure

```
NumericalMethodsWithPython/
│
├── Homework2_Numerical_Methods.ipynb
│
├── Readme.md
```

## 📊 Homework Assignment: Spline Interpolation

### Implementation Details

**🔷 Linear Spline Interpolation (1st Degree)**
- Piecewise linear interpolation between nodes
- Two node distributions: equidistant and Chebyshev-like
- Manual implementation with symbolic polynomial representation
- Error analysis at control points

**🔷 Cubic Spline Interpolation (3rd Degree)**
- Natural cubic splines with boundary conditions: $S''(x_0) = S''(x_n) = 0$
- Two implementation methods:
  - Direct definition using SciPy
  - Method of Moments (manual implementation)
- Continuity of function, first, and second derivatives
- Tridiagonal system solving for spline coefficients

**🔷 Node Distributions**
- **Equidistant nodes**: $x_k = a + k\frac{b-a}{4}, k = 0, 4$
- **Chebyshev-like nodes**: $x_k = \frac{b-a}{2} \cos\left(\frac{2k-1}{\pi}\right) + \frac{a+b}{2}, k = 1, 5$

**🔷 Error Analysis**
- Computation of absolute errors at control points
- Theoretical error bounds for linear splines
- Comparative analysis between methods and node distributions

### Example 9: Detailed Analysis

**Function**: $f(x) = e^x + \sin\left(\frac{x + 2}{2}\right)$

**Interval**: $[a, b] = [-1, 0]$

**Control Points**: $x^{(1)} = -0.29, x^{(2)} = -0.42, x^{(3)} = -0.76$

## 🛠️ Technologies Used

- **Python 3.8+**
- **NumPy**: Numerical computations and array operations
- **SciPy**: Scientific computing and spline interpolation
- **SymPy**: Symbolic mathematics and polynomial manipulation
- **Matplotlib**: Data visualization and result plotting

## 🎯 Key Features

### Symbolic Computation
```python
import sympy as sp
x = sp.Symbol('x')
# Polynomials are represented symbolically for exact form
```

### Multiple Implementation Methods
- Library-based (SciPy) and manual implementations
- Comparative validation between methods
- Educational transparency in algorithm steps

### Comprehensive Analysis
- Error calculation at specified control points
- Theoretical vs empirical error comparison
- Node distribution impact assessment

## 🚀 Getting Started

### Prerequisites
```bash
pip install numpy scipy sympy matplotlib
```

## 📈 Mathematical Foundations

### Linear Splines
For each interval $[x_i, x_{i+1}]$:
$$S_i(x) = f(x_i) + \frac{f(x_{i+1}) - f(x_i)}{x_{i+1} - x_i}(x - x_i)$$

**Error Bound**:
$$|f(x) - S(x)| \leq \frac{(x_{i+1} - x_i)^2}{8} \max_{\xi \in [x_i, x_{i+1}]} |f''(\xi)|$$

### Cubic Splines (Method of Moments)
Tridiagonal system for moments $M_i = S''(x_i)$:
$$h_{i-1}M_{i-1} + 2(h_{i-1} + h_i)M_i + h_iM_{i+1} = 6\left(\frac{f_{i+1} - f_i}{h_i} - \frac{f_i - f_{i-1}}{h_{i-1}}\right)$$

**Coefficients**:
- $a_i = f(x_i)$
- $b_i = \frac{f(x_{i+1}) - f(x_i)}{h_i} - \frac{h_i(2M_i + M_{i+1})}{6}$
- $c_i = \frac{M_i}{2}$
- $d_i = \frac{M_{i+1} - M_i}{6h_i}$

## 📊 Results Summary

### Key Findings from Example 9

1. **Cubic vs Linear Splines**:
   - Cubic splines provide significantly higher accuracy
   - Smooth second derivatives with cubic interpolation

2. **Node Distribution Impact**:
   - Chebyshev nodes often reduce maximum error
   - Better approximation near interval endpoints

3. **Method Validation**:
   - Manual Method of Moments matches SciPy implementation
   - Theoretical error bounds provide reliable estimates

4. **Performance**:
   - Linear splines: Faster computation, lower accuracy
   - Cubic splines: Higher accuracy, more computational cost

## 🔍 Error Analysis

### Control Point Errors
Computation of absolute differences between true function values and spline approximations at specified control points.

### Theoretical Bounds
Derivation and verification of mathematical error bounds for each interpolation method.

## 📝 Implementation Notes

### Code Structure
- Modular design for easy extension
- Separate modules for different spline types
- Comprehensive documentation and type hints
- Unit tests for validation

### Numerical Stability
- Careful handling of node ordering
- Robust linear system solving
- Symbolic computation for exact polynomial forms

## 🎓 Learning Objectives

### Computational Skills
- Implementation of numerical algorithms from mathematical definitions
- Understanding of polynomial interpolation theory
- Error analysis and numerical stability considerations
- Comparative method evaluation

### Programming Skills
- Scientific computing with Python
- Symbolic mathematics integration
- Data visualization and result presentation
- Code organization and documentation

*This repository represents academic work in numerical methods and computational mathematics. All implementations are educational and intended for learning purposes.*