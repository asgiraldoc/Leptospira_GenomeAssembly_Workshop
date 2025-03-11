# 01 - Data Acquisition

This tutorial provides detailed instructions for obtaining genomic sequencing data of *Leptospira interrogans* serovar Copenhageni strain FDAARGOS\_203. Both Illumina short-read and PacBio long-read sequencing data are acquired from the Sequence Read Archive (SRA) hosted by the National Center for Biotechnology Information (NCBI), followed by importing these datasets into Galaxy for subsequent analyses.

## Dataset Overview

The datasets utilized in this tutorial represent genomic sequences from a human clinical isolate collected in Brazil. The data includes Illumina paired-end reads suitable for short-read sequencing analysis and PacBio long-read sequencing data intended for hybrid assembly.

| SRA Accession | Sequencing Platform | Average Read Length | BioProject  | BioSample    | Library Type | Collection Location |
| ------------- | ------------------- | ------------------- | ----------- | ------------ | ------------ | ------------------- |
| SRR4272049    | Illumina HiSeq 2000 | 202 bp              | PRJNA231221 | SAMN04875540 | Paired-end   | Brazil              |
| SRR4272050    | PacBio RS           | 4148 bp             | PRJNA231221 | SAMN04875540 | Single-end   | Brazil              |
| SRR4272051    | PacBio RS           | 4396 bp             | PRJNA231221 | SAMN04875540 | Single-end   | Brazil              |

## Data Acquisition Steps

### 1. Downloading Data from NCBI SRA Using SRA Toolkit

#### Install SRA Toolkit

To download datasets from SRA, the SRA Toolkit provided by NCBI must be installed:

```bash
# Example for Linux/macOS
wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/current/sratoolkit.current-ubuntu64.tar.gz
tar -xzf sratoolkit.current-ubuntu64.tar.gz
export PATH=$PATH:$PWD/sratoolkit.current-ubuntu64/bin
```

#### Download FASTQ files

For Illumina paired-end data (SRR4272049):

```bash
fastq-dump --split-files --gzip SRR4272049
```

For PacBio single-end data (SRR4272050 and SRR4272051):

```bash
fastq-dump --gzip SRR4272050
fastq-dump --gzip SRR4272051
```

This results in:

- `SRR4272049_1.fastq.gz` (Illumina Read 1)
- `SRR4272049_2.fastq.gz` (Illumina Read 2)
- `SRR4272050.fastq.gz` (PacBio single-end reads)
- `SRR4272051.fastq.gz` (PacBio single-end reads)

---

### 2. Importing Data into Galaxy

After acquiring the sequencing data, upload the files to your Galaxy workspace for subsequent analysis:

1. Log in to your Galaxy instance.
2. Navigate to the **Upload Data** option located at the top of the left sidebar.
3. Select or drag the downloaded FASTQ files (`.fastq.gz`) into the upload interface.
4. Specify the file type as `fastqsanger.gz` in the upload menu.
5. Click **Start** to begin uploading your datasets.

After the upload completes, the datasets will appear in your Galaxy History, ready for further analysis.

---

## Next Steps

Proceed to remove host contamination sequences from the datasets:

→ [02. Host Sequence Removal](Host_Sequence_Removal.md)

---

## Useful References

- [NCBI Sequence Read Archive](https://www.ncbi.nlm.nih.gov/sra)
- [SRA Toolkit Documentation](https://github.com/ncbi/sra-tools/wiki)
- [Galaxy Project](https://usegalaxy.org/)

