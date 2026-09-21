# HARP - Foundations

### Summary of HARP

The HARP Project is an NIH-funded P50 Center grant in collaboration with the Center for Family Research at the University of Georgia. It is designed to transform scientific understanding regarding the causes and prevention of addictive behaviors by investigating (a) the biological and neurocognitive contributors to addictive behaviors that drive many drug use and health disparities African Americans’ experience and (b) the potential of family-centered prevention programming to ameliorate the influence of growing up in chronically stressful contexts. Our neuroimmune network (NIN) model specifies stress-induced alterations in the transactions between peripheral inflammation and neurocognitive systems that subserve emotion regulation in the development of addictive behavior vulnerability. RP1 (Transitions) provides an in-depth assessment on neural activity and inflammation and comprises a “deep dive” into mechanistic hypotheses suggested by the NIN model through a two-wave study spanning 2.5 years of African American emerging adults, ages 18-20 at baseline. 

Data collection includes bioimaging of NIN-related neural systems, assay of peripheral inflammation, and measures of stress exposure and addictive behaviors. RP2 (Foundations) conducts a pioneering longitudinal, two-year experimental trial that includes baseline and follow-up assessments with fMRI, inflammatory, and behavioral data with 300 African American youth at age 11 and their primary caregivers. This study will be able to examine empirically the underlying biological mechanisms for the multi-level benefits of family-centered prevention programming. You can learn more about the projects here.

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

