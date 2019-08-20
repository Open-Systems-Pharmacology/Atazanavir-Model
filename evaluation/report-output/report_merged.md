<h1> Building and evaluation of a PBPK model for atazanavir in healthy adults</h1>


<div style="page-break-after: always;"></div>
[toc]
# 1 Introduction
The presented model building and evaluation report evaluates the performance of a PBPK model for atazanavir in healthy adults.

Atazanavir, sold under the trade name Reyataz among others, is an azapeptide protease inhibitor and used as antiretroviral medication to treat and prevent HIV/AIDS. It is taken orally once a day at a dose of 300 mg, if co-administered with ritonavir 100 mg orally once a day, and 400 mg, if administered without ritonavir. 

After oral administration, atazanavir is rapidly absorbed. A positive food effect has been observed, atazanavir is recommended to be taken with food. Protein binding is relatively high (86%) and independent of the concentration of serum proteins ([US Food and Drug Administration 2002](# 5 References)). Atazanavir undergoes extensive metabolism by CYP3A isoenzymes with a dose fraction excreted unchanged in urine of approximately 7% ([US Food and Drug Administration 2002](# 5 References), [Le Tiec 2005](# 5 References)). Previous in vitro studies suggest that atazanavir is a mechanism-based inhibitor of CYP3A ([US Food and Drug Administration 2002](# 5 References), [Perloff 2005](# 5 References)).

The atzanavir model is a whole-body PBPK model and is - together with the respective evaluation plan and PBPK report - transparently documented and provided open-source (https://github.com/AndreDlm/Atazanavir-Model).




# 2 Methods

## 2.1 Modeling strategy
The general workflow for building an adult PBPK model has been described by Kuepfer et al. ([Kuepfer 2016](# 5 References)). 

First, a base mean model was built using plasma concentration-time profiles and the dose fraction excreted unchanged in urine following single dose administration of 400 mg po. The mean PK model was developed using a typical White American individual. Unknown parameters were identified using the Parameter Identification module provided in PK-Sim® and MoBi® ([Open Systems Pharmacology Documentation](# 5 References)). The following parameters were optimized:

- Dissolution shape
- Dissolution time (50% dissolved)
- Specific intestinal permeability (transcellular)
- GFR fraction
- CLspec/[Enzyme]

Structural model selection was mainly guided by visual inspection of the resulting description of PK data and biological plausibility. On the basis of in vitro findings, atazanavir has been suggested to be a mechanism-based inhibitor of CYP3A ([Perloff 2005](# 5 References)); however, no kinetic parameters have been reported for this interaction. Hence, to avoid non-identifiability issues, mechanism-based inhibition of CYP3A was not considered during parameter identification of the mean base model for single dose administration. All models implemented in PK-Sim for estimating the intracellular-to-plasma partition coefficient and those for estimating the permeability between interstitial and intracellular space were tested in this step. Once an appropriate structural model was identified, a second parameter identification was conducted fixing all previously optimized parameter values (except the GFR fraction) and including additional PK data following multiple dose administration of 200 mg, 300 mg, 400 mg, and 800 mg po. Optimized parameters were:

- GFR fraction
- k_kinact_half
- k_inact

The PBPK models are developed based on clinical data of healthy adult subjects obtained from the literature, covering available dosing ranges for oral administration. Plasma concentration-time profiles following multiple-dose application and mass balance information on the urinary excretion of unchanged atazanavir were included in model development. 

The performance of the PBPK model for atazanavir to describe observed PK is assessed by means of diagnostics plots and predicted versus observed concentration-time profiles, of which the results support an adequate simulation of the PK in healthy adults.

Relevant information on the anthropometry (height, weight) was gathered from the respective clinical study, if reported. Information on physiological parameters (e.g. blood flows, organ volumes, hematocrit) in adults was gathered from the literature and has been incorporated in PK-Sim® as described previously ([Willmann 2007](# 5 References)). The  applied activity and variability of plasma proteins and active processes that are integrated into PK-Sim® are described in the publicly available ‘PK-Sim® Ontogeny Database Version 7.3' ([PK-Sim Ontogeny Database Version 7.3](# 5 References)).






## 2.2 Data used
### 2.2.1	In vitro / physicochemical data

A literature search was performed to collect available information on physicochemical properties of atazanavir. The obtained information from the literature is summarized in the table below and is used for model building.

| **Parameter** | **Unit** | **Raltegravir literature**                                   | **Description**                                 |
| :------------ | -------- | ------------------------------------------------------------ | ----------------------------------------------- |
| MW            | g/mol    | 704.9 ([drugbank.ca](# 5 References))                | Molecular weight                                |
| pKa (basic)   |          | 4.7 ([Berlin 2015](# 5 References))                  | Acid dissociation constant                      |
| logP          |          | 2.12 ([Hyland 2008](# 5 References))                 | Partition coefficient between octanol and water |
| fu            |          | 0.14 ([US Food and Drug Administration 2002](# 5 References)) | Fraction unbound                                |

### 2.2.2	Clinical data

A literature search was performed to collect available PK data on atazanavir in healthy adults. 

The following publications were found and used for model building and evaluation:

| Publication                                                  | Study description                                            |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [Acosta 2007](# 5 References)                        | 300 mg atazanavir BID                                        |
| [Agarwala 2003](# 5 References)                      | 400 mg atazanavir QD                                         |
| [Agarwala 2005a](# 5 References)                     | 400 mg atazanavir QD                                         |
| [Agarwala 2005b](# 5 References)                     | 400 mg atazanavir QD                                         |
| [Martin 2008](# 5 References)                        | 400 mg atazanavir QD                                         |
| [Zhu 2010](# 5 References)                           | 300 mg atazanavir QD                                         |
| [Zhu 2011](# 5 References)                           | 400 mg atazanavir QD                                         |
| [US Food and Drug Administration 2002](# 5 References) | AI424-004 (p. 94): 400 mg atazanavir single dose; AI424-014 (p. 77): 400 mg atazanavir single dose; AI424-015 (p. 81): 400 mg atazanavir single dose; AI424-028 (p. 128): 200, 400, and 800 mg atazanavir QD; AI424-029 (p. 47): 400 mg [14C]atazanavir single dose; AI424-040 (p. 64): 200, 400, and 800 mg atazanavir QD; AI424-056 (p. 134): 300 mg atazanavir QD; AI424-076 (p. 178): 400 and 800 mg atazanavir QD |


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
# 3 Results and Discussion
The results of the first parameter identification including PK data after single dose administration (see section [2.1](## 2.1 Modeling Strategy)) described the observed PK reasonably. However, since no PK data following IV administration was available, a moderate correlation was observed between the fitted dissolution time (50% dissolved) and GFR fraction. PK profiles in fed state were generally well described, while the model overestimated Cmax in fasted state. Since atazanavir must be taken with food, the overestimation of Cmax in fasted state was considered inconsequential for further model applications which encompassed all fed state PK.

As described in section [2.1](## 2.1 Modeling Strategy), the second parameter identification was conducted in the basis of PK data after single and multiple dose administration and included autoinhibition of CYP3A4-mediated clearance. An attempt to fix k_kinact_half to a very high value (100 µmol/L) to ensure linear inhibition kinetics while fitting k_inact and the GFR faction resulted in a slightly worse description of the observed PK in the terminal phase. Hence, both k_kinact_half and k_inact were fitted together with the GFR fraction. This resulted in a strong correlation between the former two parameters, but also in a reduction of the total error from 4.76 (k_kinact_half fixed to 100 µmol/L) to 3.55 (k_kinact_half fitted). Furthermore, the introduction of irreversible CYP3A4 inhibition led to a slightly worse description of clearance of the single dose PK data. Due to the lack of data from in vitro studies, neither of the two parameters could be fixed to observed values, though, and it was decided to both fit k_kinact_half and k_inact. Results showed that the observed PK profiles were in adequate agreement with the simulated PK, although the PK after administration of the lowest and highest dose (200 and 800 mg) was somewhat less accurately described. Importantly, the PK after administration of 300 mg and 400 mg - the only two approved doses - could be adequately captured, though. 
## 3.1 Atazanavir final input parameters
The compound parameter values of the final atazanavir PBPK model are illustrated below.


### Compound: Atazanavir

#### Parameters

Name                                             | Value                   | Value Origin                            | Alternative | Default |
------------------------------------------------ | ----------------------- | --------------------------------------- | ----------- | ------- |
Solubility at reference pH                       | 50000 mg/l              | Assumption                              | Assumption  | True    |
Reference pH                                     | 7                       | Assumption                              | Assumption  | True    |
Lipophilicity                                    | 2.12 Log Units          | Publication-Hyland 2008, PMID: 18647303 | Measurement | True    |
Fraction unbound (plasma, reference value)       | 0.14                    | Publication-Rajoli 2015, PMID: 25523214 | Measurement | True    |
Specific intestinal permeability (transcellular) | 9.8649602504E-06 cm/min | Parameter Identification                | Optimized   | True    |
Is small molecule                                | Yes                     |                                         |             |         |
Molecular weight                                 | 704.8555 g/mol          | Internet-drugbank.ca                    |             |         |
Plasma protein binding partner                   | Unknown                 |                                         |             |         |
#### Calculation methods

Name                    | Value               |
----------------------- | ------------------- |
Partition coefficients  | Rodgers and Rowland |
Cellular permeabilities | PK-Sim Standard     |
#### Processes

##### Metabolizing Enzyme: CYP3A4-Optimized

Molecule: CYP3A4
###### Parameters

Name                 | Value                   | Value Origin             |
-------------------- | ----------------------- | ------------------------ |
Enzyme concentration | 1 µmol/l                |                          |
Specific clearance   | 0 1/min                 |                          |
CLspec/[Enzyme]      | 1.0383524966 l/µmol/min | Parameter Identification |
##### Systemic Process: Glomerular Filtration-Clinical Pharmacology Review

Species: Human
###### Parameters

Name         |       Value | Value Origin             |
------------ | -----------:| ------------------------ |
GFR fraction | 2.014495446 | Parameter Identification |
##### Inhibition: CYP3A4-Perloff2005

Molecule: CYP3A4
###### Parameters

Name          | Value                 | Value Origin             |
------------- | --------------------- | ------------------------ |
kinact        | 0.0033009852632 1/min | Parameter Identification |
K_kinact_half | 0.1292581489 µmol/l   | Parameter Identification |
##### Inhibition: UGT1A1-InternalData

Molecule: UGT1A1
###### Parameters

Name | Value         | Value Origin                                           |
---- | ------------- | ------------------------------------------------------ |
Ki_c | 0.1672 µmol/l | In Vitro-Calculated from reported Ki and fu,mic        |
Ki_u | 0.7524 µmol/l | In Vitro-Calculated from reported Ki, fu,mic and alpha |

## 3.2 Atazanavir Diagnostics Plots
Below you find the goodness-of-fit visual diagnostic plots for atazanavir PBPK model performance (observed versus individually simulated plasma concentration and weighted residuals versus time) of all data used for model building.


![001_plotGOFMergedPredictedVsObserved.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\002_3_2_Atazanavir_Diagnostics_Plots\001_plotGOFMergedPredictedVsObserved.png)

GMFE = 1.496554 

![003_plotGOFMergedResidualsOverTime.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\002_3_2_Atazanavir_Diagnostics_Plots\003_plotGOFMergedResidualsOverTime.png)

GMFE = 1.496554 

## 3.3 Atazanavir Concentration-Time profiles
Simulated versus observed plasma concentration-time profiles of all data are shown below.
![001_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\001_plotTimeProfile.png)

![002_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\002_plotTimeProfile.png)

![003_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\003_plotTimeProfile.png)

![004_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\004_plotTimeProfile.png)

![005_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\005_plotTimeProfile.png)

![006_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\006_plotTimeProfile.png)

![007_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\007_plotTimeProfile.png)

![008_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\008_plotTimeProfile.png)

![009_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\009_plotTimeProfile.png)

![010_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\010_plotTimeProfile.png)

![011_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\011_plotTimeProfile.png)

![012_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\012_plotTimeProfile.png)

![013_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\013_plotTimeProfile.png)

![014_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\014_plotTimeProfile.png)

![015_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\015_plotTimeProfile.png)

![016_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\016_plotTimeProfile.png)

![017_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\017_plotTimeProfile.png)

![018_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\018_plotTimeProfile.png)

![019_plotTimeProfile.png](C:\Users\gemuh.AD-BAYER-CNB\Desktop\Markdown\Atazanavir\report-output\markdown_for_pdf\003_3_Results_and_Discussion\003_3_3_Atazanavir_Concentration-Time_profiles\019_plotTimeProfile.png)

# 4 Conclusion
The  final atazanavir PBPK model applies metabolism by CYP3A4, glomerular filtration and mechanism-based inhibition of CYP3A4. While the latter process has not been evaluated using another victim compound, it should only be regarded preliminary and further work is needed before this model can be applied to predict CYP3A4 DDIs. Overall, the model adequately describes the oral pharmacokinetics of  atazanavir in healthy adults receiving approved atazanavir doses of 300 mg and 400 mg.


# 5 References
**Acosta** EP, Kendall MA, Gerber JG, Alston-Smith B, Koletar SL, Zolopa AR, et al. Effect of concomitantly administered rifampin on the pharmacokinetics and safety of atazanavir administered twice daily. *Antimicrob Agents Chemother* 2007, 51(9): 3104-3110.

**Agarwala** S, Grasela D, Child M, Geraldes M, Geiger M, O’Mara E. Characterization of the steady-state pharmacokinetic (PK) profile of atazanavir (ATV) beyond the 24-hour 
dosing interval. Poster presented at *2nd International AIDS Society Conference on HIV Pathogenesis and Treatment*, Paris, 2003. (http://www.medadvocates.org/resources/conferences/iasconfpath/ias2003/atv%20pk%20past%2024%20hour%20interval.pdf), accessed on 07-30-2019.

**Agarwala** S, Eley T, Child M, Wang Y, Hughes E, Grasela D. Pharmacokinetic effects of coadministration of atazanavir and tenofovir at steady state. Poster presented at *3rd International AIDS Society Conference on HIV Pathogenesis and Treatment*, Rio de Janeiro, 2005a. (http://www.medadvocates.org/resources/conferences/3rd%20_ias/05-156a_agarwala_086.pdf), accessed on 07-30-2019.

**Agarwala** S, Gray K, Eley T, Wang Y, Hughes E, Grasela D. Pharmacokinetic interaction between atazanavir and omeprazole in healthy subjects. Poster presented at *3rd International AIDS Society Conference on HIV Pathogenesis and Treatment*, Rio de Janeiro, 2005b. (http://www.medadvocates.org/resources/conferences/3rd%20_ias/05-156b_agarwala_109.pdf), accessed on 07-30-2019

**Berlin** M, Ruff A, Kesisoglou F, Xu W, Wang MH, Dressman JB. Advances and challenges in PBPK modeling–analysis of factors contributing to the oral absorption of atazanavir, a poorly soluble weak base. *Eur J Pharm Biopharm* 2015, 93: 267-280.

**drugbank** (https://www.drugbank.ca/drugs/DB01072), accessed on 07-30-2019.

**Hyland** R, Dickins M, Collins C, Jones H, Jones B. Maraviroc: in vitro assessment of 
drug–drug interaction potential. *Br J Clin Pharmacol* 2008, 66(4): 498-507.

**Kuepfer** L, Niederalt C, Wendl T, Schlender JF, Willmann S, Lippert J, Block M, Eissing T, Teutonico D. Applied concepts in PBPK modeling: how to build a PBPK/PD model. *CPT Pharmacometrics Syst Pharmacol* 2016, 5(10): 516-531.

**Le Tiec** C, Barrail A, Goujard C, Taburet AM. Clinical pharmacokinetics and summary of 
efficacy and tolerability of atazanavir. *Clin Pharmacokinet.* 2005, 44(10): 1035-1050.

**Martin** DE, Galbraith H, Schettler J, Ellis C, Doto J. Pharmacokinetic properties and tolerability of bevirimat and atazanavir in healthy volunteers: an open-label, parallel-group study. *Clin Ther.* 2008, 30(10): 1794-1805.

**Open Systems Pharmacology Documentation**. (https://docs.open-systems-pharmacology.org/), accessed on 07-30-2019.

**Perloff** ES, Duan SX, Skolnik PR, Greenblatt DJ, von Moltke LL. Atazanavir: effects on P-glycoprotein transport and CYP3A metabolism in vitro. *Drug Metab Dispos* 2005, 33(6): 764-770.

**PK-Sim Ontogeny Database Version 7.3**. (https://github.com/Open-Systems-Pharmacology/OSPSuite.Documentation/blob/38cf71b384cfc25cfa0ce4d2f3addfd32757e13b/PK-Sim%20Ontogeny%20Database%20Version%207.3.pdf), accessed on 07-30-2019.

**Rodgers** T, Leahy D, Rowland M. Physiologically Based Pharmacokinetic Modeling 1: Predicting the Tissue Distribution of Moderate-to-Strong Bases. *J Pharm Sci* 2005, 94: 1259-1275.

**Rodgers** T, Rowland M. Physiologically Based Pharmacokinetic Modeling 2: Predicting the Tissue Distribution of Acids, Very Weak Bases, Neutrals and Zwitterions. *J Pharm Sci* 2006, 95: 1238-1257.

**US Food and Drug Administration**. Reyataz (atazanavir) capsules: Clinical Pharmacology and Biopharmaceutics Review, Application number: 21-567, 2002. Available at: https://www.accessdata.fda.gov/drugsatfda_docs/nda/2003/021567_reyataz_toc.cfm, accessed on 07-30-2019.

**Willmann** S, Höhn K, Edginton A, Sevestre M, Solodenko J, Weiss W, Lippert J, Schmitt W. Development of a physiology-based whole-body population model for assessing the influence of individual variability on the pharmacokinetics of drugs. *J Pharmacokinet Pharmacodyn* 2007, 34(3): 401-431.

**Zhu** L, Butterton J, Persson A, Stonier M, Comisar W, Panebianco D, et al. Pharmacokinetics and safety of twice-daily atazanavir 300 mg and raltegravir 400 mg in healthy individuals. *Antivir Ther* 2010, 15(8): 1107-1114.

**Zhu** L, Persson A, Mahnke L, Eley T, Li T, Xu X, et al. Effect of low‐dose omeprazole (20 mg Daily) on the pharmacokinetics of multiple‐dose atazanavir with ritonavir in healthy subjects. *J Clin Pharmacol* 2011, 51(3): 368-377.
