**Overview**

A reproducible Snakemake workflow for identifying drought-responsive non-canonical peptides originating from untranslated regions (UTRs) of agriculturally important plant species using RNA-Seq data.

The pipeline automates:

*SRA download
Quality control
Adapter trimming
Genome indexing
RNA-Seq alignment
Transcript assembly
UTR extraction
sORF prediction
IRES detection
Expression analysis
Functional annotation*


**Software Requirements**

| Tool         | Version |
| ------------ | ------- |
| Snakemake    | ≥7      |
| HISAT2       | ≥2.2    |
| Samtools     | ≥1.17   |
| Cufflinks    | ≥2.2    |
| Bedtools     | ≥2.31   |
| gffread      | latest  |
| TrimGalore   | latest  |
| TransDecoder | latest  |
| BLAST+       | latest  |
| IRESfinder   | latest  |
| RSEM         | latest  |
| DESeq2       | latest  |
| EdgeR        | latest  |

Installation
*Clone Repository*
   
    git clone https://github.com/username/utr-peptide-pipeline.git

    cd utr-peptide-pipeline
*Install Miniconda*
   
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

    bash Miniconda3-latest-Linux-x86_64.sh
*Create Environment*
   
    conda env create -f environment.yml

    conda activate utr_peptide
    
**Example environment.yml**

name: utr_peptide

channels:
  - bioconda
  - conda-forge

dependencies:
  - snakemake
  - hisat2
  - samtools
  - cufflinks
  - bedtools
  - gffread
  - trim-galore
  - sra-tools
  - blast
  - transdecoder
  - r-base
  - bioconductor-deseq2
  - bioconductor-edger
  - 
**Directory Structure**

project/
    |── Snakefile
    ├── environment.yml
    ├── reference/
    │   ├── genome.fa
    │   └── annotation.gtf

    ├── data/

    ├── trimmed/

    ├── aligned/

    ├── cufflinks/

    ├── utr/

    ├── sorf/

    ├── blast/

    ├── results/
  
    └── logs/
    
**Running the Pipeline**
Execute
    
    snakemake --cores 16
