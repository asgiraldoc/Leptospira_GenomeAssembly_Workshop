# 04 - Hybrid Genome Assembly with SPAdes

This tutorial presents a comprehensive protocol for performing hybrid genome assembly, integrating Illumina short-read and PacBio long-read sequencing data of *Leptospira interrogans* serovar Copenhageni using SPAdes within the Galaxy platform. Hybrid assembly leverages the accuracy of short reads combined with the contiguity provided by long reads, ensuring high-quality genome assemblies.

---

## Objectives

- Conduct a hybrid genome assembly combining Illumina and PacBio sequencing data.
- Optimize SPAdes parameters within Galaxy to achieve accurate and contiguous assemblies.

---

## Prerequisites

Ensure that the following tutorials have been completed:

- [01. Data Acquisition](01_Data_Acquisition.md)
- [02. Host Sequence Removal](02_Host_Sequence_Removal.md)
- [03. Quality Control](03_Quality_Control.md)

---

## Required Input Files

- Quality-trimmed Illumina paired-end reads:
  - `trimmed_paired_R1.fastq.gz`
  - `trimmed_paired_R2.fastq.gz`
- Cleaned PacBio long-read data:
  - `host_removed_SRR4272050.fastq.gz`
  - `host_removed_SRR4272051.fastq.gz`

---

## Hybrid Assembly Workflow with SPAdes in Galaxy

### Step 1: Launch SPAdes in Galaxy

1. Access your Galaxy account.
2. From the Galaxy tool panel, locate **SPAdes** under the "Assembly" category.

### Step 2: Configure SPAdes Parameters

- **Assembly mode**: Select "Hybrid assembly".
- **Short-read input (Illumina)**:
  - Forward reads: `trimmed_paired_R1.fastq.gz`
  - Reverse reads: `trimmed_paired_R2.fastq.gz`
- **Long-read input (PacBio)**:
  - Long-read datasets: `host_removed_SRR4272050.fastq.gz`, `host_removed_SRR4272051.fastq.gz`
- **Run SPAdes in careful mode**: Yes (improves error correction and assembly accuracy).
- **k-mer sizes**: Use SPAdes defaults (recommended).

### Step 3: Execute Assembly

- Click "Run Tool" to initiate the hybrid assembly process.
- The runtime depends on the data size and available computational resources.

---

## Reviewing Assembly Output

Upon completion, SPAdes will generate several outputs:

- **contigs.fasta**: Final assembled genomic contigs.
- **scaffolds.fasta**: Assembled genomic scaffolds.
- **assembly_graph.gfa**: Graphical representation of assembly structure.

Evaluate these results in detail during the assembly evaluation phase.

---

## Next Steps

Proceed to assess assembly quality using evaluation metrics and tools:

→ [05. Assembly Evaluation](05_Assembly_Evaluation.md)

---

## Additional Resources

- [SPAdes Official Documentation](http://cab.spbu.ru/software/spades/)

