# 02 - Host Sequence Removal

This tutorial provides step-by-step instructions to effectively remove host-derived contamination sequences from genomic datasets using Galaxy. Specifically, it addresses the removal of human DNA contamination from Illumina short-read data using BWA-MEM.

---

## Objectives

- Identify and remove human genomic sequences from microbial genomic sequencing data.
- Prepare datasets free of host contamination for downstream genome assembly.

---

## Input Files (post quality control)

- Illumina paired-end sequencing reads.
- PacBio long-read sequencing data.

---

## Host Removal Workflow in Galaxy

### Step 1: Removal of Human Reads from Illumina Data Using Bowtie2

#### Obtain Human Genome Reference

1. Download pre-built Bowtie2 index of the human genome (GRCh38):

```bash
wget https://genome-idx.s3.amazonaws.com/bt/GRCh38_noalt_as.zip
unzip GRCh38_noalt_as.zip
```

2. Upload the human reference index files into Galaxy or ensure they are available on your Galaxy instance.

#### Run Bowtie2

1. In Galaxy, select **BWA-MEM** from the "Mapping" or "Alignment" tools category.
2. Set parameters as follows:
   - **Select reference genome**: human genome.
   - **Input**: Quality-controlled Illumina reads.

3. Execute the tool.

#### Resulting Files

The output includes two FASTQ files free of human reads:
- `host_removed_R1.fastq.gz`
- `host_removed_R2.fastq.gz`

These files are suitable for subsequent genome assembly analyses.

---

## Next Steps

Proceed to genome assembly using the cleaned datasets:

→ [03. Quality Control](03_Quality_Control.md)

---

## Useful References

- [Bowtie2 Manual](http://bowtie-bio.sourceforge.net/bowtie2/manual.shtml)
- [NCBI BLAST Documentation](https://blast.ncbi.nlm.nih.gov/Blast.cgi)
