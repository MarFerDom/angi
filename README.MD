# Analysis of NIDS Generalization

	The last step in an analysis of NIDS generalization between datasets of different contexts.
	Code is maintained for reproducibility of the source material and will not be improved upon nor will it be updated in any way.

## Fist step

- Clone https://github.com/c2dc/aBFF-sbseg2022 and run prior steps.

- Include the notebook files on this repository.

## MAIN FILES

> - `analyse_all_results_graphs.ipynb`
> - `analyse_all_results.ipynb`
> - `explain_selected_pairs_reduced.ipynb`


### analyse_all_results_graphs.ipynb

> Loads all results from tests with and without sampling strategies.
> Makes the nomenclature consistent.
> Calculates metrics for each result (Recall, Precision, TNR, F1-score, and MCC).
> Makes TPR and TNR, F1-score, and MCC graphs.
> Builds latex for graphs.
> Makes DT importance graphs.

### analyse_all_results.ipynb

> Similar to previous file.
> Only calculates MCC.
> Builds tables for cross-testing MCC results per model type and per source dataset.
> Builds latex for each table.

### explain_selected_pairs_reduced.ipynb

> Builds explanation models for the selected models and targets.
> Creates importance bar plots.
> Retrain models on selected features.
> Test new models.
> Make LaTeX table of results for source dataset and FS's target dataset.


# ABOUT FEATURES
## FEATURES EXTRACTION
- NB-15 extracts features from Argus and Zeek programs. featuresNB15.py joins with label file provided by the pcap source and calculates 12 extra features as described in (Moustafa et al 2015).
- CICFlowMeter extracts CIC features. featuresCIC.py joins with label file provided by the pcap source and adds Flow ID.

# SOURCE PCAP

AB-TRAP (bonafide) is extracted from MAWILab by filering with labeled file provided by the pcap source.
bonafide is split for processing in Argus/Zeek. Files must be joined before calculating group features.
attack is generated by simulation and each ip represents an attack category.
attack and bonafide datasets must be joined at the end.
attacks and traffic occur separatedly in time.

UNSW-NB15 label file NUSW-NB15_GT.csv is provided by the pcap source.
CIC-IDS2017 label files in GeneratedLabelledFlows.zip are provided by the pcap source.

# PCAPs
 Some packet capture files used/generated during aBFF development

* Original MAWILab pcap files extracted from: http://www.fukuda-lab.org/mawilab/

R. Fontugne, P. Borgnat, P. Abry, K. Fukuda. "MAWILab: Combining diverse anomaly detectors for automated anomaly labeling and performance benchmarking". ACM CoNEXT 2010. Philadelphia, PA. December 2010.

* CIC-BoT-IoT and CIC-ToN-IoT extracted from https://staff.itee.uq.edu.au/marius/NIDS_datasets/

M. Sarhan, S. Layeghy, and M. Portmann, An explainable machine learning-based network intrusion detection system for enabling generalisability in securing iot networks, 2021. arXiv:2104.07183 [cs.CR]

---
