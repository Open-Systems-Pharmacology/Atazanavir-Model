## 3.1 Atazanavir final PK parameter tables
The compound parameter values of the final atazanavir PBPK model are illustrated below.


# Compound: Atazanavir

## Parameters

Name                                             | Value                   | Value Origin                                                                                          | Alternative | Default |
------------------------------------------------ | ----------------------- | ----------------------------------------------------------------------------------------------------- | ----------- | ------- |
Solubility at reference pH                       | 50000 mg/l              | Other-Assumption-Assumption                                                                           | Assumption  | True    |
Reference pH                                     | 7                       | Other-Assumption-Assumption                                                                           | Assumption  | True    |
Lipophilicity                                    | 2.12 Log Units          | Publication-Unknown-Hyland 2008, PMID: 18647303                                                       | Measurement | True    |
Fraction unbound (plasma, reference value)       | 0.14                    | Publication-Unknown-Rajoli 2015, PMID: 25523214                                                       | Measurement | True    |
Specific intestinal permeability (transcellular) | 9.8649602504E-06 cm/min | Parameter Identification-Parameter Identification-Value updated from 'SingleDose' on 2019-07-29 17:45 | Optimized   | True    |
Is small molecule                                | Yes                     |                                                                                                       |             |         |
Molecular weight                                 | 704.8555 g/mol          | Internet-Unknown-drugbank.ca                                                                          |             |         |
Plasma protein binding partner                   | Unknown                 |                                                                                                       |             |         |
## Calculation methods

Name                    | Value               |
----------------------- | ------------------- |
Partition coefficients  | Rodgers and Rowland |
Cellular permeabilities | PK-Sim Standard     |
## Processes

### Metabolizing Enzyme: CYP3A4-Optimized

Molecule: CYP3A4
#### Parameters

Name                 | Value                   | Value Origin                                                                                          |
-------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------- |
Enzyme concentration | 1 µmol/l                |                                                                                                       |
Specific clearance   | 0 1/min                 |                                                                                                       |
CLspec/[Enzyme]      | 1.0383524966 l/µmol/min | Parameter Identification-Parameter Identification-Value updated from 'SingleDose' on 2019-07-29 17:45 |
### Systemic Process: Glomerular Filtration-Clinical Pharmacology Review

Species: Human
#### Parameters

Name         |       Value | Value Origin                                                                                                           |
------------ | -----------:| ---------------------------------------------------------------------------------------------------------------------- |
GFR fraction | 2.014495446 | Parameter Identification-Parameter Identification-Value updated from 'Single+MultipleDose_withMBI' on 2019-07-30 10:12 |
### Inhibition: CYP3A4-Perloff2005

Molecule: CYP3A4
#### Parameters

Name          | Value                 | Value Origin                                                                                                           |
------------- | --------------------- | ---------------------------------------------------------------------------------------------------------------------- |
kinact        | 0.0033009852632 1/min | Parameter Identification-Parameter Identification-Value updated from 'Single+MultipleDose_withMBI' on 2019-07-30 10:12 |
K_kinact_half | 0.1292581489 µmol/l   | Parameter Identification-Parameter Identification-Value updated from 'Single+MultipleDose_withMBI' on 2019-07-30 10:12 |

