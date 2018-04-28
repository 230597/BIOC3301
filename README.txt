# BIOC3301

This repository contains batch scripts used to submit to Cartesius HPC for the analysis of soil microbiome sequencing data using QIIME.

The scripts should be carried out in the following order:
1) joining_reads.pbs
2) split_lib_out.pbs
3) otus_closed_Silva97.pbs
4) filtering_otus.pbs
5) filtering_samples.pbs
6) cda_Silva97.pbs
7) comp_categories.pbs / group_significance.pbs

joining_reads.pbs - Joins Read1 and Read2 sequencing data to create one file for use in subsequent analyses.

split_lib_out.pbs - Carries out barcode assignment and quality filtering of samples using Phred score 20.

otus_closed_Silva97.pbs - Uses closed reference otu picking with the Silva 128 release database and 97% similarity to output a biom table for subsequent analyses.

filtering_otus.pbs - Filters the OTU biom table to remove OTUs not present in >50% samples and <0.01% total abundance in the table 

filtering_samples.pbs - Filters the new biom table to remove samples containing less than 1000 counts/sample.

cda_Silva97.pbs - Core diversity analysis of the final biom table to output taxa summaries, alpha diveristy and beta diversity metrics

comp_categories.pbs - Uses the ANOSIM stastistical method to compare soil categories with beta diversity metrics 

group_significance.pbs - Uses ANOVA statistical method to validate the differential abundance of individual species between soil sample category groupings.


