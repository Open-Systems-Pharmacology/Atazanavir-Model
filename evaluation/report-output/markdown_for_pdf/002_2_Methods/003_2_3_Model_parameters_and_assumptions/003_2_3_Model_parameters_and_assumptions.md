## 2.3 Model parameters and assumptions
### 2.3.1	Dissolution and absorption

No PK data were available following intravenous administration of atazanavir allowing informing distribution and systemic clearance independently of dissolution and absorption. Consequently, only PK data following oral administration of atazanavir as capsule were used for model building. It was assumed that solubility is not a critical parameter for dissolution of atazanvir capsules in the GI tract; in the models, solubility was therefore fixed to a very high value (50 mg/mL) to prevent solubility being a limiting factor of dissolution. Although the equilibrium solubility of atazanavir in the biorelevant media FaSSIF and FeSSIF has been observed to be rather low (2.74 µg/mL and 4.13 µg/mL in FaSSIF and FeSSIF, respectively), dissolution of atazanavir capsules in these media yields concentrations that are considerably higher than this threshold during the complete measurement period of at least 3 h ([Berlin 2015](# 5 References)). In the model, dissolution was described by a Weibull function; and the two Weibull parameters, dissolution shape and Dissolution time (50% dissolved), were fitted together with the specific intestinal permeability (transcellular) to observed PK data as described in section [2.1](## 2.1 Modeling Strategy).

### 2.3.2	Distribution

With a fraction unbound in humans of 0.14, atazanavir is extensively protein-bound. The extent of protein binding has been reported to be independent of the concentration of serum proteins ([US Food and Drug Administration 2002](# 5 References)). The observed PK data were found to be best described using the model for estimating intracellular-to-plasma partition coefficients by Rodgers et al. ([Rodgers 2005](# 5 References), [Rodgers 2006](# 5 References)) and the cellular permeability automatically calculated by PK-Sim® ([Open Systems Pharmacology Documentation](# 5 References)). 

### 2.3.3	Elimination

Atazanavir is extensively metabolized via CYP3A isoenzymes ([Le Tiec 2005](# 5 References)). Metabolism was modeled as linear process mediated by CYP3A4 ('in vitro clearance - first order'). The gene expression profile of CYP3A4 was loaded from the internal PK-Sim® database using the expression data quantified by RT-PCR ([Open Systems Pharmacology Documentation](# 5 References)). 

Following oral administration of 400 mg [14C]atazanavir to healthy males, approximately 7% of the radioactive dose were recovered as unchanged drug in the urine ([US Food and Drug Administration 2002](# 5 References)). Renal excretion of the unchanged drug was modeled as glomerular filtration process. The GFR fraction was then, together with the specific clearance via CYP3A4 normalized to the enzyme concentration (CLspec/[Enzyme]), fitted to observed PK data as described in section [2.1](## 2.1 Modeling Strategy).

### 2.3.2	Autoinhibition

Findings from in vitro studies indicate that atazanavir irreversibly inhibits CYP3A ([US Food and Drug Administration 2002](# 5 References), [Perloff 2005](# 5 References)). Since no kinetic values were reported for this mechanism-based inhibition, relevant parameters in the model (k_kinact_half and k_inact) were fitted as described in section [2.1](## 2.1 Modeling Strategy).
