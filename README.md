# ParaHostEnv

# Data and Code Description

## Data Used

**main_experiment**  
Downloaded from: https://doi.org/10.1111/pim.12898  
Repository: https://datashare.ed.ac.uk/handle/10283/3937  

File name:  
“Measures of parasite density, ring density and host health for main rescheduling experiment”

---

## Code

### `model_selection_code/`
Code for running multiple model variants:
- 5 parameter model  
- 5 parameter + cycle length model  
- 5 parameter + ring duration model  
- 5 parameter + inflection point model  
- 5 parameter + inflection point + ring duration model  

These scripts were used to run optimization on the BioHPC cluster.  

**Outputs:**
- `model_selection_param_values/`
- `model_selection_fitted_dynamics/`

---

### `synthetic_data_fitting_code/`
Code for running optimization using the:
- 5 parameter + inflection point + ring duration model  

Applied to 100 synthetic datasets for each treatment group using the BioHPC cluster.  

**Outputs:**
- `synthetic_dataset_fits/`
- `synthetic_dataset_param/`

---

### `Figures&Tables.Rmd`
Contains all code required to generate:
- Figures
- Tables (main text and supplementary materials)

**Note:**  
The code is organized in the order experiments were conducted, not by manuscript figure/table numbering.

---

## Fitted Outcome Data

### `model_selection_param_values/`
Contains the **best three fitted parameter sets**, including:

- `par`: parameter values in the order:
  - shape (s)
  - offset (o)
  - parasite multiplication rate (R)
  - number of compartments (n)
  - inoculum size (I0)
  - cycle length (c)
  - inflection point (p3)
  - ring duration (rL)

- `value`: sum of squared error  
- `iter`: number of iterations to converge  
- `convergence`: convergence code  
- `message`: details on convergence/termination  

---

### `model_selection_fitted_dynamics/`
Fitted dynamics from the best parameter sets for each treatment group:

- `circ_iRBC`: circulating infected red blood cells  
- `seq_iRBC`: sequestered infected red blood cells  
- `ring_prop_estim`: estimated ring-stage proportion  

---

### `synthetic_dataset_fits/`
Fitted dynamics for 100 synthetic datasets:

- `circ_iRBC`: circulating iRBCs  
- `seq_iRBC`: sequestered iRBCs  
- `ring_prop_estim`: ring percentage  

---

### `synthetic_dataset_params/`
Best fitted parameter sets for the 100 synthetic datasets.

- Results are split across **4 tables** covering all datasets.
