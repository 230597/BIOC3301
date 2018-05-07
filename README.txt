# BIOC3301

This repository contains batch scripts used to submit to the Cartesius HPC for the analysis of Illumina MiSeq soil microbiome sequencing data using QIIME 1.9.1.
This set of scripts is used to determine patterns of bacterial abundance and diversity with soil metadata categories.

Analysis Workflow Order:

1) joining_reads.pbs - Joins Read1 and Read2 sequencing data to create one file for use in subsequent analyses.
2) split_lib_out.pbs - Carries out barcode assignment and quality filtering of samples using Phred score 20.
3) otus_closed_Silva97.pbs - Uses closed reference otu picking with the Silva 128 release database and 97% similarity to output a biom table for subsequent analyses.
4) filtering_otus.pbs - Filters the OTU biom table to remove OTUs not present in >50% samples and <0.01% total abundance in the table 
5) filtering_samples.pbs - Filters the new biom table to remove samples containing less than 1000 counts/sample.
6) cda_Silva97.pbs - Carries out core diversity analysis of the final biom table to output taxa summaries, alpha diveristy and beta diversity metrics.
7) comp_categories.pbs - Uses the ANOSIM stastistical method to compare soil categories using beta diversity matrices.
8) group_significance.pbs - Uses ANOVA statistical method to validate the differential abundance of individual species between soil sample category groupings.


