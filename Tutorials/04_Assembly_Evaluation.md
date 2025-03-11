# 04 - Assembly Evaluation

This tutorial provides guidelines for evaluating the quality and completeness of the hybrid genome assembly of *Leptospira interrogans* serovar Copenhageni performed using SPAdes in Galaxy. Proper evaluation is essential to determine the reliability and usability of the assembled genome.

---

## Objectives

- Assess the quality and completeness of the assembled genome.
- Interpret key assembly metrics such as N50, total length, and completeness scores.

---

## Required Input

- Assembly output file (`contigs.fasta` or `scaffolds.fasta`) generated in the [previous tutorial](Hybrid_Assembly.md).

---

## Step-by-Step Assembly Evaluation in Galaxy

### Step 1: Evaluating Assembly Quality with QUAST

QUAST provides a comprehensive set of metrics useful for evaluating genome assemblies.

1. In Galaxy, locate the **QUAST** tool under the "Assembly" or "Quality Control" section.
2. Select your assembly file (`contigs.fasta` or `scaffolds.fasta`) as the input.
3. Configure QUAST parameters:
   - **Minimum contig length**: 500 bp (recommended)
   - **Reference genome** (optional): Provide if available for comparative metrics.
4. Click **Run Tool** to initiate analysis.

### Interpreting QUAST Results

QUAST will produce a comprehensive report containing:
- Total number of contigs and scaffolds
- N50 metric (indicative of assembly contiguity)
- Total genome length
- Number and size distribution of contigs and scaffolds

Review the generated HTML report to evaluate these metrics comprehensively.

### Example metrics interpretation:

- **N50**: Larger values generally indicate better assembly contiguity.
- **Total length**: Ideally close to the expected genome size for *Leptospira interrogans* (~4.6 Mb).
- **Number of contigs/scaffolds**: Fewer and longer contigs typically reflect a higher-quality assembly.

---

## Step 2: Genome Completeness Assessment Using BUSCO

BUSCO evaluates genome completeness by identifying conserved single-copy orthologs.

1. In Galaxy, locate and select **BUSCO** under the "Assembly" or "Annotation" category.
2. Select your assembly file as the input.
3. Choose appropriate lineage dataset (e.g., "Bacteria") for benchmarking completeness.
4. Run BUSCO.

BUSCO provides completeness statistics as percentages of:

- **Complete** (single-copy and duplicated orthologs)
- **Fragmented**
- **Missing orthologs**

A high percentage of complete BUSCO orthologs (>90%) suggests a robust assembly suitable for downstream analysis.

---

## Next Steps

With assembly quality and completeness verified, you may proceed to advanced analyses such as genome annotation and comparative genomics.

---

## Additional Resources

- [QUAST Official Documentation](http://quast.sourceforge.net/)
- [BUSCO Official Documentation](https://busco.ezlab.org/)
