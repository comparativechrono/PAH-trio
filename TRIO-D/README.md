# Coursework data: the TRIO-D family

These are exome sequencing reads from a family of three. The proband, TRIO-D_2-1, is male and has pulmonary arterial hypertension (PAH). His father (TRIO-D_1-2) and his mother (TRIO-D_1-1) are well, and there is no known family history of PAH.

The data are for teaching. They are based on publicly available sequencing data from volunteers who consented to its open use, with changes made for this coursework, so they don't come from a real patient.

## Files

| File | What it is |
|---|---|
| `data/proband/TRIO-D_2-1_R1.fastq.gz`, `data/proband/TRIO-D_2-1_R2.fastq.gz` | Reads from the proband |
| `data/parents/TRIO-D_1-2_R1.fastq.gz`, `data/parents/TRIO-D_1-2_R2.fastq.gz` | Reads from the father |
| `data/parents/TRIO-D_1-1_R1.fastq.gz`, `data/parents/TRIO-D_1-1_R2.fastq.gz` | Reads from the mother |
| `md5sums.txt` | Checksums, so you can check the files downloaded completely (`md5sum -c md5sums.txt`) |

## About the reads

- Whole-exome capture, sequenced on an Illumina HiSeq 2500 as 2 × 126 bp paired-end reads. Unlike the genome data you used in the practicals, the reads cluster on the exons, with little coverage between them.
- The files contain only the reads from the six regions of the course data. Over the coding exons the depth is about 110x.
- All three samples were sequenced on lane 5 of flowcell CA9KRANXX, as the read names show. Give each sample its own read group.
- Use the course reference genome, `~/GM5_family/reference/GRCh38_GM5.fa`. It already has the indexes that BWA and GATK need.
- The reads cover the same regions as the course data, so the course's own resource files in `~/GM5_family/resources` work for every step that takes regions, known sites or gene annotation, as they do in the Practical 7 pipeline.
