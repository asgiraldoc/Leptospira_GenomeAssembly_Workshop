# 02 - Quality Control

This tutorial outlines the procedures for conducting quality control and read trimming on genomic sequencing data from *Leptospira interrogans* serovar Copenhageni using Galaxy. Ensuring high-quality sequencing data is crucial for accurate downstream analyses, including genome assembly.

---

## Objectives

- Evaluate the quality of Illumina short-read and PacBio long-read sequencing data.
- Trim adapters and low-quality bases from Illumina sequencing reads.

---

## Tools Used

- **FastQC**: For quality assessment of sequencing reads.
- **Trimmomatic**: To trim adapters and low-quality bases from Illumina sequencing reads.

---

## Step-by-step Procedure

### Step 1: Assess Initial Quality with FastQC

1. In Galaxy, locate and select the tool **FastQC** under "Quality Control."
2. Select the uploaded Illumina sequencing data (`SRR4272049_1.fastq.gz` and `SRR4272049_2.fastq.gz`).
3. Execute FastQC by clicking "Run Tool."
4. Review the generated FastQC reports to identify potential issues such as adapter contamination, low-quality bases, or irregular sequence content.

### Step 2: Trimming Illumina Reads Using Trimmomatic

1. Select **Trimmomatic** under the "Quality Control" section in Galaxy.
2. Configure Trimmomatic parameters as follows:
   - **Input files**: Paired-end Illumina data (`SRR4272049_1.fastq.gz` and `SRR4272049_2.fastq.gz`).
   - **Perform initial ILLUMINACLIP step?**: Yes (select appropriate adapter sequences based on Illumina platform).
   - **Sliding window trimming**: Yes (recommended: 4 bases window, minimum quality 20).
   - **Leading and trailing minimum quality**: 3
   - **Minimum length of reads**: 36
3. Click "Run Tool" to start the trimming process.
4. Four output files will be generated:
   - Forward paired-end reads (`trimmed_paired_R1.fastq.gz`)
   - Reverse paired-end reads (`trimmed_paired_R2.fastq.gz`)
   - Forward unpaired reads (usually discarded)
   - Reverse unpaired reads (usually discarded)

### Step 3: Re-assess Quality Post-trimming with FastQC

1. Repeat the FastQC analysis on the trimmed Illumina paired-end reads to verify improvements in quality.
2. Confirm successful adapter removal and quality enhancement by comparing pre- and post-trimming FastQC reports.

### Step 4: Quality Check for PacBio Reads (optional)

PacBio long-read sequencing data typically requires minimal trimming. However, a preliminary quality check with FastQC can be beneficial to evaluate general sequencing quality and length distribution:

1. Use FastQC to analyze PacBio data (`SRR4272050.fastq.gz` and `SRR4272051.fastq.gz`).
2. Review FastQC results for quality overview and potential contamination issues.

---

## Next Steps

After completing quality control and trimming, proceed to hybrid genome assembly:

→ [03. Hybrid Assembly with SPAdes](Hybrid_Assembly.md)

---

## Useful Resources

- [FastQC documentation](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
- [Trimmomatic documentation](http://www.usadellab.org/cms/?page=trimmomatic)
