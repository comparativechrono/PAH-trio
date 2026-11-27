# Coursework data: the TRIO-B family

These are exome sequencing reads from a family of three. The proband, TRIO-B_2-1, is male and has pulmonary arterial hypertension (PAH). His father (TRIO-B_1-2) and his mother (TRIO-B_1-1) are well, and there is no known family history of PAH.

The data are for teaching. They are based on publicly available sequencing data from volunteers who consented to its open use, with changes made for this coursework, so they don't come from a real patient.

## Files

| File | What it is |
|---|---|
| `data/proband/TRIO-B_2-1_R1.fastq.gz`, `data/proband/TRIO-B_2-1_R2.fastq.gz` | Reads from the proband |
| `data/parents/TRIO-B_1-2_R1.fastq.gz`, `data/parents/TRIO-B_1-2_R2.fastq.gz` | Reads from the father |
| `data/parents/TRIO-B_1-1_R1.fastq.gz`, `data/parents/TRIO-B_1-1_R2.fastq.gz` | Reads from the mother |
| `resources/TRIO-B_regions_GRCh38.bed` | The seven regions the reads cover |
| `resources/TRIO-B_coding_exons.bed` | The coding exons of the seven genes the regions are named after |
| `resources/TRIO-B_MANE_genes.gff3.gz` | The MANE Select transcripts of the genes in the regions, for `bcftools csq` |
| `resources/dbsnp157_TRIO-B.vcf.gz`, `resources/Mills_1000G_indels_TRIO-B.vcf.gz` | Known sites over the seven regions, for base recalibration, with their indexes |
| `md5sums.txt` | Checksums, so you can check the files downloaded completely (`md5sum -c md5sums.txt`) |

## About the reads

- Whole-exome capture, sequenced on an Illumina HiSeq 2500 as 2 × 126 bp paired-end reads. Unlike the genome data you used in the practicals, the reads cluster on the exons, with little coverage between them.
- The files contain only the reads from seven regions: the six regions of the course data and a seventh on chromosome 2. Over the coding exons the depth is about 100x.
- All three samples were sequenced on lane 2 of flowcell CB4T7ANXX, as the read names show. Give each sample its own read group.
- Use the course reference genome, `~/GM5_family/reference/GRCh38_GM5.fa`. It already has the indexes that BWA and GATK need.
- The course's resource files cover only the six course regions. Use the files in `resources/` instead, for every step that takes regions, known sites or gene annotation. If you use the Practical 7 pipeline, point its config at them.
