# Gamma Ray Buildup Factor Simulation

This repository contains a Python implementation of a simulation to compute gamma-ray buildup factors and final intensities for various materials using Monte Carlo methods. The program models photon interactions (absorption, scattering) within a material slab and calculates the photon buildup factor based on initial parameters.

---

## Features

- Calculate linear attenuation coefficients (μ) for different materials (Aluminum, Lead, Iron, Tungsten).
- Simulate photon scattering and absorption using Monte Carlo methods.
- Compute gamma-ray buildup factors for user-defined slab thickness and incident photon energy.
- Evaluate final photon intensities for various materials.

---

## Requirements

- Python 3.x
- NumPy

Install the required libraries using:
```bash
pip install numpy
```

---

## Usage

### 1. Parameters
Modify the following parameters in the script as needed:
- `muL`: Thickness of the slab in mean free paths.
- `E0`: Energy of incident gamma photons in MeV.
- `N`: Number of photons to simulate.

Example default values:
```python
muL = 2.0  # Slab thickness in mean free paths
E0 = 1.0  # Energy of incident photons in MeV
N = 10**6  # Number of photons to simulate
```

### 2. Run the Simulation
Run the script to calculate the buildup factors and final intensities for the following materials:
- Aluminum
- Lead
- Iron
- Tungsten

```bash
python gamma_ray_buildup.py
```

### 3. Output
The program outputs the gamma-ray buildup factor and final intensity for each material:
```plaintext
Buildup Factor for Aluminum: 1.23
Buildup Factor for Lead: 1.56
...
Final Intensity for Aluminum: 0.34
Final Intensity for Lead: 0.67
...
```

---

## Functions

### `AttnCoeffs(E, material)`
Computes the linear attenuation coefficients (μ) for a given photon energy and material.

- **Inputs**:
  - `E`: Photon energy [MeV]
  - `material`: Material name (Aluminum, Lead, Iron, Tungsten)
- **Outputs**:
  - `muT`: Total attenuation coefficient [cm^-1]
  - `muC`: Compton scattering coefficient [cm^-1]

---

### `calculate_buildup_factor(material, muL, E0, N)`
Simulates photon interactions and calculates the buildup factor for a specified material and slab thickness.

- **Inputs**:
  - `material`: Material name
  - `muL`: Slab thickness in mean free paths
  - `E0`: Initial photon energy [MeV]
  - `N`: Number of photons to simulate
- **Output**:
  - `BF`: Gamma-ray buildup factor

---

## Example Results
For a slab thickness of 2 mean free paths and incident photon energy of 1 MeV:

```plaintext
Buildup Factor for Aluminum: 1.25
Buildup Factor for Lead: 1.58
Buildup Factor for Iron: 1.40
Buildup Factor for Tungsten: 1.65

Final Intensity for Aluminum: 0.45
Final Intensity for Lead: 0.35
Final Intensity for Iron: 0.38
Final Intensity for Tungsten: 0.31
```

---


