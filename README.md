# HARP - Foundations

### Summary of HARP

There is a scientific consensus emerging that developmental exposures to social adversity can promote drug use vulnerabilities through cumulative effects on neurobiological and peripheral systems.

The Health and Resilience Project (HARP) is an NIH-funded P50 Center research program that aims to investigate how chronic stress exposure, experienced through social adversity, affects the biological and psychological development of children and young adults. HARP aims at investigating how this toll manifests in escalating rates of addictive behavior, including drug use and unhealthy eating.

The African American populations on whom the P50 Center and Research Project 2 (RP2) focus are disproportionately exposed to such social adversities. The proposed P50 continues and expands the pioneering work of the Center for Translational and Prevention Science (CTAPS) through two avenues:

    (a) Biological and Neurobiological - Investigating the biological and neurobiological contributors to addictive behaviors that drive many drug use and health disparities African Americans experience.

    Here we ask: How does chronic stress get under the skin to heighten vulnerability to addictive behaviors, including drug use and unhealthy eating, and the cardiometabolic health conditions that such behaviors generate? To begin to address this question, CTAPS scientists proposed a neuroimmune network (NIN) model highlighting bidirectional signaling between the brain and immune system in the pathophysiology of addictive behaviors.

    (b) Family-centered Prevention Programming - Conducting studies that illuminate the potential of family-centered prevention programming to ameliorate the pernicious and persistent influence of growing up in chronically stressful contexts.


The mechanisms and processes investigated in the P50 are not limited to African American populations; we expect them to have broad applicability in furthering scientific understanding of the etiology and prevention of addictive behavior among other US populations exposed to chronic stress.


### HARP Research Projects

To address these objectives, HARP comprises two complementary research projects:

**TRANSITIONS (RP1) — Emerging Adulthood (Ages 18–20 at baseline):** Examines how chronic stress exposure influences neuroimmune functioning and vulnerability to addictive behaviors during the transition to adulthood, with a focus on the biological pathways linking social adversity to adverse health outcomes.

**FOUNDATIONS (RP2) — Childhood and Early Adolescence (Age 11 at baseline):** Investigates how chronic stress exposure affects neuroimmune development and whether family-centered prevention programming can mitigate these effects and reduce vulnerability to addictive behaviors.

## FOUNDATIONS: Neuroimaging Data Processing Workflow

The FOUNDATIONS repository contains scripts used to organize, prepare, and preprocess neuroimaging data collected as part of Research Project 2 (RP2) of HARP:

1. **MRI Data Conversion and BIDS Organization:** Converting raw MRI data into NIfTI format and organizing the resulting files according to BIDS conventions.
   - `scripts/bidsprocessing/dir_to_nifti.sh` — Converts MRI data from DICOM to NIfTI format.
   - `scripts/bidsprocessing/dirs_to_nifti.sh` — Supports conversion of multiple MRI directories.
   - `scripts/tartobids.py` — Converts and organizes MRI scans into BIDS-style directories. This represents an alternative conversion and organization pathway.
   - `scripts/bidskit.sh` — Runs BIDSkit to support BIDS organization.
   - `scripts/movebidstoclean.py` — Copies organized imaging and behavioral files into their designated study directories.

2. **De-identification and Data Preparation:** Removing identifying information from imaging files and preparing the data for subsequent processing.
   - `scripts/harp_pih_remover.py` — Renames and organizes imaging files to remove participant names from filenames.
   - `scripts/bidsprocessing/deface.sh` — Runs defacing on T1-weighted anatomical MRI images to remove facial features.

3. **MRI Quality Control (MRIQC):** Assessing the quality of structural and functional MRI data to identify potential imaging artifacts and data quality concerns.
   - `scripts/foundations_mriqc.sh` — Runs MRIQC for an individual participant.
   - `scripts/tabulate_mriqc.py` — Intended to consolidate MRIQC metrics from JSON files into a CSV file.

4. **fMRI Preprocessing (fMRIPrep):** Preparing functional MRI data for subsequent statistical analysis through preprocessing procedures, including motion correction, anatomical-functional registration, and spatial normalization.
   - `scripts/fmriprep/fmripreploop.sh` — Reads a participant list and submits individual fMRIPrep processing jobs.
   - `scripts/fmriprep/fmriprepsinglepartic.sh` — Executes fMRIPrep for an individual participant.

