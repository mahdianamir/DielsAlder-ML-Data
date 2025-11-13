## 🧾 Dataset Description



The dataset includes **1,000 Diels–Alder reactions** between various dienes and dienophiles, computed at the DFT level.  
Each entry contains 54 variables describing structural, electronic, and energetic features relevant to reactivity and selectivity.
The numbers **1–9** represent the following substituents:  


1: F (Fluorine), 2: CN (Cyano), 3: OCH₃ (Methoxy), 4: CH₃ (Methyl), 5: C(CH₃)₃ (tert-Butyl), 6: H (Hydrogen),  
7: Ph (Benzene), 8: COOCH₃ (Methoxycarbonyl), 9: CHO (Formyl).

### Main Columns

- **diene**, **dienophile** – molecular identifiers for each reaction pair.  
- **ΔG TS_endo_1 / ΔG TS_exo_1 / ΔG TS_endo_2 / ΔG TS_exo_2** – DFT-computed activation free energies (kcal·mol⁻¹) for both endo and exo transition states.  
- **ΔG Product_endo/exo** – relative free energies of the endo and exo adducts.  
- **HOMO_D**, **LUMO_D** – frontier orbital energies (eV) of the diene.  
- **pz_pop_C1–C4_D** – electron populations on the 2p orbitals of the four diene carbons.  
- **Σp₁–₄_D (Sigma p constants)** – Hammett-type substituent constants capturing electronic effects along the diene backbone.  
- Additional descriptors include geometric and electronic attributes used as input features for the ML models.

### Notes

- All energies were calculated at the **SMD/M06-2X/def2-TZVP//SMD/M06-2X/6-31G(d)** level of theory.  
- The target variable for model training is **ΔG‡ (activation barrier)** corresponding to the lowest-energy transition state (endo/exo).  
- The dataset was used to train gradient boosting and random forest regression models on **13 attribute-based descriptors**, selected via SHAP feature-importance analysis.


