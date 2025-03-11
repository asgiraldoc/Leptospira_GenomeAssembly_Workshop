# 03 - Hybrid Genome Assembly with SPAdes

This tutorial provides detailed instructions for performing a hybrid genome assembly using Illumina short-read and PacBio long-read sequencing data from *Leptospira interrogans* serovar Copenhageni, using the SPAdes assembler within the Galaxy platform. Hybrid assembly combines the accuracy of short reads with the longer contiguity provided by PacBio sequencing, enhancing the completeness and accuracy of the genome reconstruction.

---

## Objectives

- Conduct a hybrid genome assembly integrating Illumina and PacBio data.
- Understand and apply SPAdes parameters within the Galaxy platform.

---

## Prerequisites

Ensure completion of the following steps prior to beginning this tutorial:

- [01. Data Acquisition](01_Data_Acquisition.md)
- [02. Quality Control](02_Quality_Control.md)

## Required Input Data

- Trimmed Illumina paired-end reads (e.g., `trimmed_paired_R1.fastq.gz`, `trimmed_paired_R2.fastq.gz`).
- PacBio long-read sequencing data (`SRR4272050.fastq.gz` and `SRR4272051.fastq.gz`).

---

## Step-by-step Hybrid Assembly

### Step 1: Selecting SPAdes in Galaxy

1. Log into your Galaxy workspace.
2. From the tools panel, locate and select **SPAdes** under the "Assembly" category.

### Step 2: Configuring SPAdes Parameters

- **Run mode**: Select "Hybrid assembly".
- **Short-read input**:
  - Select trimmed Illumina paired-end data (`trimmed_paired_R1.fastq.gz`, `trimmed_paired_R2.fastq.gz`).
- **Long-read input**: Select PacBio sequencing files (`SRR4272050.fastq.gz`, `SRR4272051.fastq.gz`).
- **Assembly mode**: Choose "careful" to optimize assembly quality.
- **k-mer lengths**: Use default values, or manually specify if desired (recommended: leave as default).
- **Resource usage**: Adjust CPU and memory usage according to available computational resources.

### Step 2: Running SPAdes Assembly

- After verifying all input parameters, execute SPAdes by clicking "Run Tool."
- Assembly may take considerable time depending on data size and computational resources.

### Step 2: Reviewing SPAdes Output

SPAdes will generate several output files:
- `contigs.fasta`: Final assembled contigs.
- `scaffolds.fasta`: Scaffolds assembled from contigs.
- `assembly_graph.gfa`: Graphical representation of the assembly.

Review these files and assess the integrity and quality of assembly outputs in subsequent steps.

---

## Next Steps

Proceed to evaluate the quality of your genome assembly:

→ [04. Assembly Evaluation](Assembly_Evaluation.md)

---

## Useful Resources

- [SPAdes Official Documentation](http://cab.spbu.ru/software/spades/)
