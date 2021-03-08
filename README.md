##README

The data used were acquired on ArrayExpress (reference E-MTAB-8905, https://www.ebi.ac.uk/arrayexpress/experiments/E-MTAB-8905/samples/?query=zika).

The study reproduced is “Using Next Generation Sequencing to Study the Genetic Diversity of Candidate Live Attenuated Zika Vaccines” (DOI : https://doi.org/10.3390/vaccines8020161) by Natalie D Collins, Chao Shan, Bruno T D Nunes, Steven G Widen, Pei-Yong Shi, Alan D T Barrett, Vanessa V Sarathy  , and is accessible here : https://www.mdpi.com/2076-393X/8/2/161/htm.

Please see this file as a shorter version of the provided report found in the docs directory and see to the provided project pipeline .png for a simplified look at the project data processing pipeline.

In this repository are provided all the scripts used for the reproduction of the initial study. They must be run in this order respectively:

- **data_acquisition.Rmd:** This notebook downloads and unzips the data files from ArrayExpress. It also prepares a test data set which is used by the following scripts for faster run times.

- **simplifying_metadata.Rmd:** This notebook simplifies the metadata file generated with the script data_acquisition.Rmd by removing the unwanted strains or passages for the study. This notebook can be used if you want to simplify the data set and focus on the study of one or several strains/passages, but it is not mandatory to do so.It generates a .txt file that will be used in the script delete_files_from_list.Rmd to delete the undesired files.

- **delete_files_from_list.Rmd**: This notebook deletes files that were not used in the project. This includes the raw data files for the 3'_20 and 3'_30 deletion mutants. 

- **study_pipeline.Rmd:** This script executes the pipeline described in the section “Material and Methods” of the report. It is written for a test data set and can be run from start (QC preprocessing) to finish (Shannon entropy calculation). The test data set is generated in the data_acquisition.Rmd script and consist of a pair-end read for WTZIKV P0. The script is written so that it is run with the data directory as its working directory.

- **result_vizualisation.Rmd:** This notebook allows the analysis and visualization the results obtained from the study_pipeline.Rmd. The figures generated can be seen in the section “Results” of the report.


 

