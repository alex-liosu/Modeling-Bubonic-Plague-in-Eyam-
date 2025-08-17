# Modeling Bubonic Plague in Eyam

## 📖 Introduction
This project focuses on modeling the **bubonic plague epidemic in Eyam, England (1665–1666)**, using epidemiological models to estimate the spread and mortality of the disease. Eyam is well known for its self-imposed quarantine during the plague, which cost the lives of at least 260 residents out of a population of about 800【53†source】.

The objective was to fit mathematical models to historical burial data, gaining insights into the transmission and mortality of the plague.

## ⚙️ Methodology
We applied two classic epidemiological frameworks:

### 1. **SIR Model (Susceptible–Infected–Removed/Dead)**
- Modeled epidemic dynamics using Ordinary Differential Equations (ODEs).
- Parameters estimated via:
  - **Nonlinear Least Squares (NLS)**
  - **Bayesian Inference** (Hamiltonian Monte Carlo in RStan).
- Bayesian priors included Jeffreys priors for β, γ, and Normal/Truncated Normal priors for initial states.

### 2. **SIRD Model (Susceptible–Infected–Recovered–Dead)**
- Extended SIR by distinguishing **recovered** vs. **dead** compartments.
- Estimated using both NLS and Bayesian methods with more flexible priors.

## 📊 Results
### **SIR Model Findings**
- NLS estimates:
  - β ≈ 0.176, γ ≈ 0.107, I₀ ≈ 4
  - Basic Reproduction Number **R₀ ≈ 1.65**
- Bayesian estimates:
  - β ≈ 0.16 (95% CI: 0.14–0.19)
  - γ ≈ 0.10 (95% CI: 0.08–0.12)
  - R₀ ≈ 1.61 (95% CI: 1.42–1.86)
  - Initial infected I₀ ≈ 4.7 (95% CI: 3.5–6.3)【53†source】

### **SIRD Model Findings**
- NLS estimates:
  - β ≈ 0.067, δ ≈ 0.011, I₀ ≈ 130
  - R₀ ≈ 5.96
- Bayesian estimates:
  - β ≈ 0.15 (95% CI: 0.138–0.172)
  - γ ≈ 0.062 (95% CI: 0.041–0.095)
  - δ ≈ 0.012 (95% CI: 0.004–0.017)
  - R₀ ≈ 2.06 (95% CI: 1.70–2.54)
  - Mortality rate estimated at **73–96%**【53†source】

## ✅ Conclusion
- Both **SIR and SIRD** models can capture the epidemic dynamics in Eyam.
- **Bayesian methods** provided more reliable uncertainty quantification compared to NLS.
- The **SIRD model** is more appropriate since it explicitly accounts for survival vs. death.
- Estimated epidemic parameters:
  - β ∈ (0.138, 0.172)
  - γ ∈ (0.041, 0.095)
  - δ ∈ (0.004, 0.017)
  - R₀ ∈ (1.70, 2.54)
- Suggests that the plague did not have 100% mortality in Eyam.

## 📚 References
- Historical records of the Eyam plague (1665–1666).
- WHO guidelines on infectious disease modeling.
- RStan documentation for Bayesian inference.

