
#  Master of Pores – Day 2 Basecalling & Mapping

First - check if you have nextflow installed.

```
nextflow -version
```
If not, install it this way:
```
cd ~
wget https://github.com/nextflow-io/nextflow/releases/download/v25.04.0/nextflow
chmod +x nextflow
mkdir -p ~/bin
mv nextflow ~/bin/
echo 'export PATH=$HOME/bin:$PATH' >> ~/.bashrc
source .bashrc
```
---


##  Basecall your pod5 files with Dorado 

Navigate to the pre-processing directory:

```bash
cd ~/MOP4/mop_preprocess
```

Edit the  `params.yaml` file

Run the pipeline!

```bash
nextflow run mop_preprocess.nf -params-file params.yaml -with-singularity -profile local -bg > demultiplexing.log
```

##  Basecall your pod5 files with Dorado 

Navigate to the pre-processing directory:

```bash
cd ~/MOP4/mop_preprocess
```

Edit the  `params.yaml` file

Run the pipeline!

```bash
nextflow run mop_preprocess.nf -params-file params.yaml -with-singularity --nv -profile local -bg > demultiplexing.log
```

## Explore the bam files with samtools 

Some useful commands: 

```bash
samtools view file.bam | wc –l 
samtools view –F 4 file.bam | wc –l 
samtools view –s 0.1 file.bam | wc –l

samtools view –H file.bam | less
samtools view –h file.bam > file.sam

samtools view –Sb file.sam > new_file.bam
```

## Predict isoform usage with Isoquant 

For each bam file we can assign reads to knwon isoforms:

```bash
IsoQuant/isoquant.py --reference Share/references/chr19.fa --genedb Share/references/chr19_annotation.gb --complete_genedb --bam Share/data/mouse/output/dorado_fast/alignment/pod5---bc_1_s.bam --data_type nanopore -o isoquant_bc1
```

## Discover isoforms with Isoquant

```bash 
isoquant.py --reference ~/Share/references/chr19.fa --fastq ~/Share/data/mouse/output/dorado_fast/fastq_files/pod5---bc_1.fq.gz --data_type nanopore -o isoquant_discovery_test
```

##  Documentation

Full documentation:  
[[https://biocorecrg.github.io/master_of_pores/](https://biocorecrg.github.io/master_of_pores/MOP4-dev/index.html)]
