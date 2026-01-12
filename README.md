# C++ for Finance – Option Pricing Framework

## 📌 Project Overview

This project implements a **C++ option pricing framework** covering several fundamental models used in quantitative finance.  
It was developed as part of the **C++ for Finance** course (2025) and focuses on **object-oriented design**, **numerical methods**, and **financial modeling**.

The framework supports:
- Closed-form pricing (Black–Scholes)
- Tree-based pricing (Cox–Ross–Rubinstein)
- Monte Carlo simulation
- European, Digital, Asian, and American options

---

## 🧠 Main Features

### 1️⃣ Object-Oriented Option Design
- Abstract base class `Option`
- Clear inheritance hierarchy:
  - European Vanilla Options (Call / Put)
  - Digital Options
  - Asian Options (path-dependent)
  - American Options
- Polymorphic payoff handling (`payoff`, `payoffPath`)
- Runtime checks for incompatible pricing methods

---

### 2️⃣ Black–Scholes Pricing
- Closed-form pricing for:
  - Vanilla European options
  - Digital options
- Computation of:
  - Option price
  - Delta
- Numerical stability using STL math functions

---

### 3️⃣ Binomial Tree Pricing (CRR Model)
- Generic `BinaryTree<T>` template
- Backward induction pricing
- Supports:
  - European options
  - American options (with early exercise policy)
- Optional **closed-form CRR pricing**
- Arbitrage checks enforced at construction

---

### 4️⃣ Monte Carlo Pricing
- Monte Carlo pricer for:
  - European options
  - Asian (path-dependent) options
- Black–Scholes path simulation
- Online estimation (no path storage)
- 95% confidence interval computation
- Centralized RNG via a singleton Mersenne Twister

---

### 5️⃣ Black–Scholes as Limit of Binomial Trees
- Binomial tree initialization using Black–Scholes parameters
- Comparison between:
  - Closed-form prices
  - CRR prices
  - Monte Carlo estimates
