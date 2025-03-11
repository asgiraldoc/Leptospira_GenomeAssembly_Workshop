# Hybrid Genome Assembly Tutorial Using Galaxy: *Leptospira interrogans* Serovar Copenhageni

This repository provides tutorials, resources, and guidance for conducting hybrid genome assembly analyses using **Leptospira interrogans serovar Copenhageni** as a case study. All computational analyses presented herein utilize the Galaxy platform, a user-friendly web-based environment for bioinformatics.

## Overview

This tutorial series guides the user through the complete workflow for genomic data acquisition, preprocessing, hybrid genome assembly (combining Illumina short-read and PacBio long-read sequencing technologies), and subsequent assembly evaluation. 

## Organism Description

- **Organism:** *Leptospira interrogans*  
- **Serovar:** Copenhageni  
- **Strain:** FDAARGOS_203  
- **Isolation Source:** Clinical isolate (Human), Brazil  
- **Original Publication:** https://www.nature.com/articles/s41467-019-11306-6 
## Workflow Outline

This tutorial is structured around the following key analytical steps:

1. **Data Acquisition**: Retrieving Illumina and PacBio sequencing datasets from public databases.
2. **Host Sequence Removal**: Eliminating contaminant host sequences (human genome sequences) using Bowtie2 (Illumina) and BLASTn (PacBio).
3. **Quality Control**: Quality assessment and trimming of sequencing reads.
4. **Hybrid Genome Assembly**: Genome assembly using SPAdes, incorporating both Illumina and PacBio reads.
5. **Assembly Evaluation**: Quality and completeness assessment of the assembled genome using standard evaluation metrics and tools (QUAST).

## Data Source Information

The genomic sequencing data utilized in this tutorial is publicly accessible through the NCBI Sequence Read Archive (SRA). Relevant dataset information is summarized below:

| SRA Accession | Sequencing Platform | BioProject | BioSample     | Instrument          | Library Layout | Collection Site |
|---------------|---------------------|------------|---------------|---------------------|----------------|-----------------|
| [SRR4272049](https://www.ncbi.nlm.nih.gov/sra/SRX2179272[accn])    | Illumina HiSeq 2000 | PRJNA231221 | SAMN04875540 | FDAARGOS_203        | Paired-end     | Brazil          |
| [SRR4272050](https://www.ncbi.nlm.nih.gov/sra/SRX2179274[accn])    | PacBio RS           | PRJNA231221 | SAMN04875540 | FDAARGOS_203        | Single-end     | Brazil          |
| [SRR4272051](https://www.ncbi.nlm.nih.gov/sra/SRX2179273[accn])    | PacBio RS           | PRJNA231221 | SAMN04875540 | FDAARGOS_203        | Single-end     | Brazil          |

## Tutorials

Detailed, step-by-step tutorials are provided for each analytical component:

- [01. Data Acquisition](Tutorials/01_Data_Acquisition.md): Instructions for downloading genomic data and importing into Galaxy.
- [02. Host Sequence Removal](Tutorials/02_Host_Sequence_Removal.md): Methods for removal of human contamination using Bowtie2 for Illumina data and BLAST-based strategies for PacBio sequences.
- [03. Quality Control](Tutorials/03_Quality_Control.md): Guidelines for assessing and trimming reads based on quality metrics.
- [04. Hybrid Assembly with SPAdes](Tutorials/04_Hybrid_Assembly.md): Comprehensive protocol for hybrid genome assembly integrating Illumina and PacBio data using SPAdes.
- [05. Assembly Evaluation](Tutorials/05_Assembly_Evaluation.md): Evaluating assembly quality and completeness through metrics such as N50, genome coverage, QUAST statistics, and BUSCO completeness assessments.

## Additional Resources

- [Galaxy Workflow Files](https://usegalaxy.org/u/asgiraldoc/w/hybrid-genome-assembly-tutorial-using-galaxy)
