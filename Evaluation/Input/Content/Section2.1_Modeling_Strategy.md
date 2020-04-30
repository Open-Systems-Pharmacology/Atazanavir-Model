The general workflow for building an adult PBPK model has been described by Kuepfer et al. ([Kuepfer 2016](#5-References)). Relevant information on the anthropometry (height, weight) was gathered from the respective clinical study, if reported. Information on physiological parameters (e.g. blood flows, organ volumes, hematocrit) in adults was gathered from the literature and has been incorporated in PK-Sim® as described previously ([Willmann 2007](#5-References)). The  applied activity and variability of plasma proteins and active processes that are integrated into PK-Sim® are described in the publicly available ‘PK-Sim® Ontogeny Database Version 7.3' ([PK-Sim Ontogeny Database Version 7.3](#5-References)).

The PBPK model was developed based on clinical data of healthy adult subjects obtained from the literature, covering available dosing ranges for oral administration. Plasma concentration-time profiles following multiple-dose application and mass balance information on the urinary excretion of unchanged atazanavir were included in model development. 

First, a base mean model was built using plasma concentration-time profiles and the dose fraction excreted unchanged in urine following single dose administration of 400 mg po. The mean PK model was developed using a typical White American individual. Structural model selection was mainly guided by visual inspection of the resulting description of data and biological plausibility. The following parameters were identified using the Parameter Identification module provided in PK-Sim® and MoBi® ([Open Systems Pharmacology Documentation](#5-References)):

- `Dissolution shape`
- `Dissolution time (50% dissolved)`
- `Specific intestinal permeability (transcellular)`
- `GFR fraction`
- `CLspec/[Enzyme]`

Structural model selection was mainly guided by visual inspection of the resulting description of PK data and biological plausibility. On the basis of in vitro findings, atazanavir has been suggested to be a mechanism-based inhibitor of CYP3A ([Perloff 2005](#5-References)); however, no kinetic parameters have been reported for this interaction. Hence, to avoid non-identifiability issues, mechanism-based inhibition of CYP3A was not considered during parameter identification of the mean base model for single dose administration. All models implemented in PK-Sim for estimating the intracellular-to-plasma partition coefficient and those for estimating the permeability between interstitial and intracellular space were tested in this step. Once an appropriate structural model was identified, a second parameter identification was conducted fixing all previously optimized parameter values (except the `GFR fraction`) and including additional PK data following multiple dose administration of 200 mg, 300 mg, 400 mg, and 800 mg po. Optimized parameters were:

- `GFR fraction`
- `k_inact`
- `k_kinact_half`

Of note, since neither *in vitro* data on the kinetics of the mechanism-based inhibition of CYP3A nor *in vivo* pharmacokinetic data on drug-drug-interactions (DDI) with a CYP3A index substrate and atazanavir as CYP3A-perpetrator were available, the model should **not** be used to predict CYP3A DDI studies unless it has been verified for this purpose.

Details about input data (physicochemical, *in vitro* and clinical) can be found in [Section 2.2](#22-Data).

Details about the structural model and its parameters can be found in [Section 2.3](#23-Model-Parameters-and-Assumptions).





