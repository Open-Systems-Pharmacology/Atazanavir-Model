## 3.1 Atazanavir final input parameters
The compound parameter values of the final atazanavir PBPK model are illustrated below.


# Compound: Atazanavir

## Parameters

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
## Calculation methods

Name                    | Value               |
----------------------- | ------------------- |
Partition coefficients  | Rodgers and Rowland |
Cellular permeabilities | PK-Sim Standard     |
## Processes

### Metabolizing Enzyme: CYP3A4-Optimized

Molecule: CYP3A4
#### Parameters

Name                 | Value                   | Value Origin             |
-------------------- | ----------------------- | ------------------------ |
Enzyme concentration | 1 µmol/l                |                          |
Specific clearance   | 0 1/min                 |                          |
CLspec/[Enzyme]      | 1.0383524966 l/µmol/min | Parameter Identification |
### Systemic Process: Glomerular Filtration-Clinical Pharmacology Review

Species: Human
#### Parameters

Name         |       Value | Value Origin             |
------------ | -----------:| ------------------------ |
GFR fraction | 2.014495446 | Parameter Identification |
### Inhibition: CYP3A4-Perloff2005

Molecule: CYP3A4
#### Parameters

Name          | Value                 | Value Origin             |
------------- | --------------------- | ------------------------ |
kinact        | 0.0033009852632 1/min | Parameter Identification |
K_kinact_half | 0.1292581489 µmol/l   | Parameter Identification |
### Inhibition: UGT1A1-InternalData

Molecule: UGT1A1
#### Parameters

Name | Value         | Value Origin                                           |
---- | ------------- | ------------------------------------------------------ |
Ki_c | 0.1672 µmol/l | In Vitro-Calculated from reported Ki and fu,mic        |
Ki_u | 0.7524 µmol/l | In Vitro-Calculated from reported Ki, fu,mic and alpha |

