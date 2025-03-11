# 03 - Quality Control

This tutorial outlines the necessary steps for assessing and improving the quality of genomic sequencing data from *Leptospira interrogans* serovar Copenhageni using Galaxy. Quality control (QC) ensures reliable and accurate results in subsequent analyses, particularly genome assembly.

---

## Objectives

- Perform initial quality assessment of sequencing reads.
- Remove low-quality bases and adapter sequences from Illumina sequencing data.

---

## Tools Employed

- **FastQC**: Evaluates sequencing data quality.
- **Trimmomatic**: Removes adapters and trims low-quality sequences from Illumina reads.

---

## Quality Control Workflow

### Step 1: Initial Quality Assessment with FastQC

1. Log in to Galaxy and select the **FastQC** tool from the "Quality Control" toolset.
2. Select your sequencing files (`host_removed_R1.fastq.gz` and `host_removed_R2.fastq.gz`).
3. Execute FastQC by clicking "Run Tool."
4. Analyze generated FastQC reports focusing on:
   - Per-base quality scores.
   - Adapter contamination.
   - Overrepresented sequences.

### Step 2: Trimming Reads with Trimmomatic

Trimmomatic enhances sequencing quality by removing adapters and trimming bases with low-quality scores.

1. Select **Trimmomatic** from Galaxy’s "Quality Control" tool category.
2. Configure parameters:
   - **Paired-end reads**: Input `host_removed_R1.fastq.gz` and `host_removed_R2.fastq.gz`.
   - **ILLUMINACLIP**: Select the appropriate adapter sequences (typically TruSeq3).
   - **SLIDINGWINDOW**: Set to 4-base window, minimum average quality of 20.
   - **LEADING and TRAILING**: Set to a minimum quality score of 3.
   - **MINLEN**: Set minimum read length post-trimming to 36 bases.
3. Run Trimmomatic to generate trimmed paired-end reads:
   - `trimmed_paired_R1.fastq.gz`
   - `trimmed_paired_R2.fastq.gz`

### Step 3: Post-trimming Quality Reassessment

1. Run **FastQC** again on trimmed data (`trimmed_paired_R1.fastq.gz` and `trimmed_paired_R2.fastq.gz`).
2. Compare results before and after trimming to confirm improved read quality and removal of contaminants.

---

## Next Steps

Proceed to hybrid genome assembly using the trimmed and quality-controlled reads:

→ [04. Hybrid Genome Assembly with SPAdes](Hybrid_Assembly.md)

---

## Useful Resources

- [FastQC Documentation](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
- [Trimmomatic Documentation](http://www.usadellab.org/cms/?page=trimmomatic)
