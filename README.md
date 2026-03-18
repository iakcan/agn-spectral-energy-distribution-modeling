# AGN Spectral Energy Distribution Modeling using Bayesian MCMC

This project implements and evaluates a Bayesian SED-fitting approach for Active Galactic Nuclei (AGN), based on the AGNfitter framework, applied to real multi-wavelength observational data.

---

## Project Overview

Active Galactic Nuclei (AGN) are powered by accretion onto supermassive black holes and emit across the entire electromagnetic spectrum.

This project models AGN Spectral Energy Distributions (SEDs) by decomposing observed flux into physically interpretable components using Bayesian inference and MCMC sampling.

---

## Dataset

The dataset includes multi-wavelength observations across:

- UV, Optical, IR, Radio, X-ray
- Objects: **Mrk493 (Seyfert 1)**, **Mrk876 (Quasar-like AGN)**

Each entry contains flux values and uncertainties across spectral bands.

👉 Dataset sample:  
:contentReference[oaicite:0]{index=0}

---

## Methodology

### SED Decomposition

The total emission is modeled as:

\[
F_{total} = F_{BBB} + F_{torus} + F_{stellar} + F_{cold\ dust}
\]

Components:

- Accretion Disk (BBB)
- Dusty Torus
- Stellar Population
- Starburst (Cold Dust)

---

### Bayesian Framework

\[
P(\theta | data) \propto P(data | \theta) \cdot P(\theta)
\]

- MCMC Sampling (emcee)
- Posterior estimation
- Parameter uncertainty quantification

---

## Results

---

### 🔵 Mrk493 — Seyfert 1 Galaxy

#### SED Fit

![SED Mrk493](./SED_manyrealizations_Mrk493.pdf)

- Excellent fit across optical and IR regions
- Log-likelihood: **-22.8** :contentReference[oaicite:1]{index=1}
- Residuals centered around zero → strong model performance

#### Residual Analysis

- Minor deviations at low/high frequencies
- Generally stable fit across spectrum  
:contentReference[oaicite:2]{index=2}

#### Parameter Insights

- Metallicity: ~1.20
- Stellar Age: ~9.5 Gyr
- Dust Temp: ~32 K
- Strong AGN contribution (~86%) :contentReference[oaicite:3]{index=3}

---

### 🔴 Mrk876 — Quasar-like AGN

#### SED Fit

![SED Mrk876](./SED_manyrealizations_Mrk876.pdf)

- Strong AGN + starburst contribution
- Log-likelihood: **-276.2** :contentReference[oaicite:4]{index=4}
- More complex and harder to fit

#### Residual Analysis

- Large deviations at low & high frequencies
- Example:
  - High-frequency residuals ~ +9 → strong mismatch :contentReference[oaicite:5]{index=5}

#### Parameter Insights

- Stellar Mass: ~10¹¹ M☉
- SFR: very high (~227)
- High IR luminosity
- AGN fraction ~93% :contentReference[oaicite:6]{index=6}

---

## Posterior Analysis (Bayesian Insight)

### Corner Plots

#### Mrk493

![Corner Plot Mrk493](./PDFtriangle_10pars.pdf)

#### Mrk876

![Corner Plot Mrk876](./PDFtriangle_10pars.pdf)

These plots show:

- Parameter distributions
- Uncertainty ranges
- Correlations (e.g. dust temperature vs starburst strength)

Example:
- Strong parameter constraints visible in posterior peaks
- Some parameters show degeneracy due to model structure :contentReference[oaicite:7]{index=7}

---

## Key Insights

- Bayesian MCMC effectively captures uncertainty and parameter degeneracy
- AGN-dominated systems (Mrk493) are easier to model
- Starburst-heavy systems (Mrk876) introduce complexity
- Model struggles at:
  - High frequencies (UV/X-ray)
  - Low frequencies (radio)

---

## Tech Stack

- Python
- NumPy / SciPy
- Matplotlib
- emcee (MCMC)
- AGNfitter

---

## Future Work

- Improve high-frequency modeling
- Extend dataset size
- Incorporate deep learning-based SED approximations
- Improve priors for better convergence

---

## Author

**Irem Akcan**  
M.Sc. Data Science | Software Project Manager | Agile Coach
