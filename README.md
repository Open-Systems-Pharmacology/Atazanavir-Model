# Atazanavir-Model
Whole-body PBPK model of atazanavir as UGT1A1 perpetrator drug.

<a title="Atazanavir" href="https://commons.wikimedia.org/wiki/File:Atazanavir_structure.svg"><img width="256" alt="Atazanavir structure" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/Atazanavir_structure.svg/256px-Atazanavir_structure.svg.png"></a>

This repository contains:

- a PK-Sim snapshot (*.json) file of the current PBPK model
- static content (e.g. text blocks, *.md files) as inputs for an evaluation plan
- an evaluation plan (evaluation-plan.json) to create an evaluation report using the snapshot and static text blocks to display the performance of the model

**The latest release of the snapshot of the model, the evaluation plan and the static content can be found [here](https://github.com/Open-Systems-Pharmacology/Atazanavir-Model/releases/latest).**

**The latest release of the PK-Sim project model file and the respective evaluation report can be found [here](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library/releases).**

This atazanavir model is intended to be used as perpetrator drug in UGT1A1-mediated drug-drug interactions (DDI). 

This  whole-body atazanavir PBPK model comprises metabolim by CYP3A4, glomerular filtration and mechanism-based inhibition of CYP3A4 (this inhibition has not been evaluated and is hence to be regarded preliminary; further work is needed before this model can be applied to predict CYP3A4 DDIs). The atazanavir PBPK model has been developed and evaluated based on clinical data obtained from the scientific literature for oral administration of single or multiple doses ranging from 200 - 800 mg. 

## Code of conduct
Everyone interacting in the Open Systems Pharmacology community (codebases, issue trackers, chat rooms, mailing lists etc...) is expected to follow the Open Systems Pharmacology [code of conduct](https://github.com/Open-Systems-Pharmacology/Suite/blob/master/CODE_OF_CONDUCT.md#contributor-covenant-code-of-conduct).

## Contribution
We encourage contribution to the Open Systems Pharmacology community. Before getting started please read the [contribution guidelines](https://github.com/Open-Systems-Pharmacology/Suite/blob/master/CONTRIBUTING.md#ways-to-contribute). If you are contributing code, please be familiar with the [coding standard](https://github.com/Open-Systems-Pharmacology/Suite/blob/master/CODING_STANDARDS.md#visual-studio-settings).

## License
The model code is distributed under the [GPLv2 License](https://github.com/Open-Systems-Pharmacology/Suite/blob/develop/LICENSE).
